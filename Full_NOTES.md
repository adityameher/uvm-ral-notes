# UVM_RAL

- UVM BUIT-In Sequences
  - [Register Sequences](#h1.1)
  - Memory Seqeuences
  - Register And Memory Seqeuneces
  - Skip Attributes
- 

---
## UVM Built-In Sequences

### Register Seqeuences 
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

### Skip Attribute
```sv
uvm_resource_db#(bit)::set("REG::yapp_rm.yapp_router_regs.*_cnt_reg","NO_REG_ACCESS_TEST,1,this");
// Resource database                Scope                                 AttributeName

```
### uvm_reg_mem_built_in_seq
This sequence runs all buit in sequences except HDL paths.
We can customize the sequence list using tests property.
```sv
  uvm_reg_mem_built-in_seq reg_mem_aditya;
  task body();
    `uvm_create(reg_mem_aditya);
    reg_mem_aditya.model=yapp_rm;
    reg_mem_aditya.tests= UVM_DO_ALL_REG_MEM_TESTS & ~(UVM_DO_REG_ACCESS); // run all tests except uvm reg access seq
    `uvm_send(reg_mem_aditya)
  endtask
```
---













