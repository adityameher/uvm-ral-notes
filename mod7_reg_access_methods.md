Register Model Stores mutliple values for each field.
  - Desired "What we want in DUT"
  - Mirrored "What we think is in DUT , Prediction keeps it updated"
  - Reset  "Stores Rest values"
  - Values "used in randomization"

Desiered is identical to mirrored except in update process.

```sv

  tb.yapp_rm.router_yapp_regs.ctrl_reg.write();
  // Testbench -> Register Model -> Register Block -> Register - Method

  uvm_status_e status;
  yapp_regs.ctrl_reg.write(status,8'h20); // status is needed but checked and used internally

```

---

Backdoor DUT Access : Peek/Poke
```sv
yapp_regs.addr0_cnt_reg.poke(status,8'h20);  // backdoor write
yapp_regs.addr0_cnt_reg.peek(status,rdata); // backdoor read
```
Both ignore access policy
poking read only bit succeeds.
peeking Read on clear bit leaves the value unchanged.

---

### Standard Accesibilty checks

RW Register Check
```sv
uvm_status_e status;
yapp_regs.en_reg.write(status,'8'hA5);
#20ns; //allow write to complete
yapp_regs.en_re.peek(status,rdata);  // check now if rdata same as write value

yapp_reg s.en_reg.poke(status,'h74);
yapp_regs.en_reg.read(status,rdata); // read value same as poke value.
```
RO Register Check
```sv
Poke -> Read -> check same or not -> Write -> peek but return value should be same as original poe value
```






















