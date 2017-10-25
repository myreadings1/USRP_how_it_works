# USRPB210_how_it_works

- Blockdiagram of USRP E312, which is similar to the architecture of B210, is shown in [1] (Picture is attached).
- Definitions:
- The "sampling rate" is the rate at which samples are passed between the host commuter and the USRP (over USB for B210, and via and internal FPGA interface for E310).
- The "master_clock_rate" is the rate at which samples are passed between FPGA and the RF front end (In the case of B210 and E310 that RF fronted is an RFIC that contains analog RF circuits, converters and DSP).

- Change master_clock_rate see [3]
- Some info about FPGA see this video [4]
- Whats is an FPGA [5]?
- WiKi FPGA [6]
- Whats is a DDC and DUC? See [7]
- Knowledge base about USRP [8]



- Reference links:
- https://www.ettus.com/product/details/USRP-E312
- http://lists.ettus.com/pipermail/usrp-users_lists.ettus.com/2015-July/015109.html
- http://files.ettus.com/manual/page_usrp_b200.html
- https://youtu.be/8POZhFHxBLs
- https://www.xilinx.com/products/silicon-devices/fpga/what-is-an-fpga.html
- https://en.wikipedia.org/wiki/Field-programmable_gate_array
- https://en.wikipedia.org/wiki/Digital_down_converter
- https://kb.ettus.com/Knowledge_Base
