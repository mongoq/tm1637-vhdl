Hi mongoq,

One of my colleague faced with Quartus2 error with "tm1637_standalone.vhd" file:
...
Error (10346): VHDL error at tm1637_standalone.vhd(231): formal port or parameter "in_digit0" must have actual or default value
...
After he fixed line# 231it works OK.

Fix details:
 -> was:
      when 65 => scl <= '0'; sda <= int_to_seg7(display, 2, 2), reg_digit0, reg_digit1, reg_digit2, reg_digit3;
 -> now:
      when 65 => scl <= '0'; sda <= int_to_seg7(display, 2, 2, reg_digit0, reg_digit1, reg_digit2, reg_digit3);

I think you should know about this problem in your source code when assembling with Quartus2 software.

With best regards,
Igor K.

---

Kann ich jedoch nicht nachvollziehen.