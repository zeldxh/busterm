# busterm

university project — data structures course. bus terminal management system built with pure java: all data structures (linked lists, priority queues, weighted directed graphs) implemented from scratch without the java collections framework.

## tech stack

| | |
|---|---|
| language | java 24 |
| build | maven |
| json serialization | gson 2.8.9 |
| ui | swing (`JOptionPane`) |
| data structures | linked lists, priority queue, weighted directed graph |

## system flow

1. **startup** — checks for `config.json`
2. **initial setup** — if not found, prompts for terminal name, bus count and two user credentials
3. **login** — authenticate with configured credentials
4. **main menu** — access to all modules

## how to run

```bash
mvn compile exec:java
```

### first run

the system will ask for:
- terminal name
- number of buses (minimum 3 — 1 priority, 1 direct, the rest normal)
- user 1 and password
- user 2 and password

this is saved to `config.json` and will not be asked again.

### bccr credentials (module 1.5)

the exchange rate module requires credentials for the costa rica central bank web service.
before running, edit `ServicioBCCR.java` and replace the placeholders:

```
BCCR_NOMBRE  →  name registered with bccr
BCCR_EMAIL   →  email registered with bccr
BCCR_TOKEN   →  bccr access token
```

### generated data files

| file | contents |
|---|---|
| `config.json` | system configuration (terminal, buses, users) |
| `tiquetes.json` | pending ticket queue |
| `atendidos.json` | attended ticket history |
| `colas.txt` | people count per bus queue |
| `grafo.json` | route graph between localities |

## module status

| module | description | status |
|---|---|---|
| 1.0 | data structure configuration | ✅ |
| 1.1 | ticket creation | ✅ |
| 1.2 | ticket attendance | ✅ |
| 1.3 | queue filling | ✅ |
| 1.4 | complementary services (graphs) | ✅ |
| 1.5 | exchange rate query (bccr) | ✅ |

## documentation

- [modules](./docs/en/modules.md) — goals, features and requirements per module
- [architecture](./docs/en/architecture.md) — class overview, file tree and method reference
- [changelog](./docs/en/changelog.md) — fixes and improvements per submission

## license

MIT License, see [LICENSE](LICENSE).
