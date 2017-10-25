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
- USRP general info [9]
- Getting started with UHD and C++ [10]

-Q how to set the RF front end bandwith? Answer: set_rx_bandwidth() See [11] 
- Note: set_rx_bandwidth() ws not working previously, See [12]

- We use this cmd to get 2 Msps for Bluetooth signal
- sudo ./rx_samples_to_file --args master_clock_rate=56e6 --rate=2e6 --bw=56e6 --wirefmt=sc8 --progress --freq=2400e6
- More about decimationa dn interpolation see [13]
- Some Err messages with sampling rate
- UHD Warning:
    The requested decimation is odd; the user should expect CIC rolloff.
    Select an even decimation to ensure that a halfband filter is enabled.
    decimation = dsp_rate/samp_rate -> 19 = (56.000000 MHz)/(3.000000 MHz)

- UHD Warning:
    The hardware does not support the requested RX sample rate:
    Target sample rate: 3.000000 MSps
    Actual sample rate: 2.947368 MSps

- Some description about aliasing see [14]
- Reference links:
- https://www.ettus.com/product/details/USRP-E312
- http://lists.ettus.com/pipermail/usrp-users_lists.ettus.com/2015-July/015109.html
- http://files.ettus.com/manual/page_usrp_b200.html
- https://youtu.be/8POZhFHxBLs
- https://www.xilinx.com/products/silicon-devices/fpga/what-is-an-fpga.html
- https://en.wikipedia.org/wiki/Field-programmable_gate_array
- https://en.wikipedia.org/wiki/Digital_down_converter
- https://kb.ettus.com/Knowledge_Base
- https://kb.ettus.com/About_USRP_Bandwidths_and_Sampling_Rates
- https://kb.ettus.com/Getting_Started_with_UHD_and_C%2B%2B
- http://files.ettus.com/manual/page_usrp_b200.html
- http://lists.ettus.com/pipermail/usrp-users_lists.ettus.com/2015-February/012688.html
- http://lists.ettus.com/pipermail/usrp-users_lists.ettus.com/2012-September/005313.html
- https://www.youtube.com/watch?v=sSrfq7uvkZ4
