---

- we need to check memory aliasing that is 1 address access multiple addreses.
- what do we check inside a register environment.
  - check register and memory addressing
  - check reset
  - check field offsets
  - check access
  - check memory width
  - check functionality
---
- UVM provides base class for helping in modelling a register transaction
              <img width="732" height="353" alt="image" src="https://github.com/user-attachments/assets/89758e4f-40a5-4cef-b395-0892f28abfb4" />
- Hierarchial Architecture.
- Capture Register Attribute.
- Link a name to address (rather than using a address just use name).
- Hold Expected values for checking.
- Support Multiple address maps(where registers/memories are accesible via multiple physical interfaces).
- Register Coverage , Reusable within and betwwen projects.

- Read/Write/Randomize Regiter model.
- Frontdoor and Backdoor access.
- Register Operation is independent of bus protocol.
- Built-In Sequences for common Register operations
  - Read/Write Testing
  - Bit-Bashing
  - Memory Test Patterns

---

Address Maps -  Defines the regsiters and their characterstics as seen through one ineterface to the DUT.
  - Multiple Interfaces may access the DUT Registers
  - Register may be accesible via several interfaces
    - With Different Address
    - With Different Access Policy
  - A registers "view" for an interface is defined in an address map

---
