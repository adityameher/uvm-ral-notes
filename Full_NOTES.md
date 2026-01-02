# UVM_RAL

- UVM BUIT-In Sequences
  - [Register Sequences](#h11)
  - Memory Seqeuences
  - Register And Memory Seqeuneces
  - Skip Attributes
- 




h

h
g
g
g
g
gg
g
g
g
g
g

g
g
g
g

g
g
g
g
g
g
## UVM Built-In Sequences

### Register Seqeuences {h11}
```sv
  uvm_reg_hw_reset_seq // reads all registers in a block and read back their value after an reset.
  uvm_reg_bit_bas_seq // seqeuntially writes 0 and 1 to every bit in register check if set/cleared or not.
  uvm_reg_access_seq // write frontdorr and read backdoor then viceversa.
  uvm_reg_shared_access_seq // For each addres map where register is present , write via one map read back via another.
```
### Memory Sequences
```sv
  uvm_mem_access_seq //write frontdoor and read backdoor then vice versa.
  uvm_mem_shared_access_seq // write via one address mpa and read back via another.
  uvm_mem_walk_seq // write walking pattern seq into mem and read back.
```
### Register And Memory Seqeunces
```sv
  uvm_reg_mem_access_seq // execute register and then memeory access seqeunces.
  uvm_reg_mem_shared_access_seq // same like before execute shared reg seq then shared me  seq.
  uvm_reg_mem_hdl_paths_seq // check if the backdoor paths are indeed accesible by the sim.
```
Register access policies are respected by Buit in Seqeuences


