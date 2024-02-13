# Agenda Backlog

## Action Items

- ACTION: do we move any issues from public `security` repo?

## Agenda Items

- general policy on outside collaborators joining the meeting
- Strategies used and features/invariants relied upon to write secure programs today (Michael Ficarra)
- Adopting something like the W3C Self-Review Questionnaire: Security and Privacy
  - IETF has a similar doc: <https://datatracker.ietf.org/doc/html/rfc3552>
- open issues: <https://github.com/tc39/security/issues>
- outreach
- private issues in security repo
- Discoverability of hidden intrinsics (Mathieu Hofman)
- How to mark spec internal objects as not exposed to user code (Mathieu Hofman)
- Discussion: what threat models should we be considering? what is "security" to this group? (Michael Ficarra)
- secure contexts (feature availability determined by scheme (http/s)) - <https://github.com/WICG/uuid/issues/23>
  - discuss/form committee opinion on secure contexts
- Supply chain risk. The greatest risk that JS should address. NPM reports that only 3% are only specific to the application and 97% are libraries.
- TC53 collaboration opportunities
  - TC53 is standardizing on hardened JS
  - Strong encapsulation is needed. Threat models are adversarial. Treat libraries as an adversary.
  - LavaMoat (set of tools for securing JavaScript projects against a category of attacks called software supply chain attacks)
    - <https://www.npmjs.com/package/lavamoat>
    - <https://github.com/LavaMoat/LavaMoat>
  - JHD: what i like about LavaMoat's approach is that it reduces the set of "potential package vectors" from "all deps" down to "only deps that already legitimately have dangerous permissions", which drastically reduces the manual auditing/review work required.
- Explore language capabilities that are undeniable, not virtualizable. (MF)
- proposals
  - review security impact of (Shared) Structs proposal - <https://github.com/tc39/proposal-structs>
    - and [WasmGC shared memory proposal](https://github.com/WebAssembly/shared-everything-threads/blob/main/proposals/shared-everything-threads/Overview.md)
  - does TC39 need a formal security review for proposals?
    - related issues on this:
      - <https://github.com/tc39/security/issues/4>
      - <http://github.com/tc39/process-document/pull/18>
- MM: Existing code can run in hardened mode
  - biggest problem with running existing code in hardened mode wrt builtins is overriding
    - find a means to suppress override mistake (if possible)
      - if not possible, introduce something to language to create context/realm
    - JHD: changing to accessers can break packages <https://github.com/ljharb/call-bind/issues/4>
- MAH: need a private place to discuss... private things
  - feedback while discussing making the TG3 repo public
