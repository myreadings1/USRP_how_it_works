# USRPB210_how_it_works

- Blockdiagram of USRP E312, which is similar to the architecture of B210, is shown in [1] (Picture is attached).
- Definitions:
- The "sampling rate" is the rate at which samples are passed between the host commuter and the USRP (over USB for B210, and via and internal FPGA interface for E310).
- The "master_clock_rate" is the rate at which samples are passed between FPGA and the RF front end (In the case of B210 and E310 that RF fronted is an RFIC that contains analog RF circuits, converters and DSP).



Maurizio

The "sampling rate" is the rate at which samples are passed between the host commuter and the USRP (over USB for B210, and via and internal FPGA interface for E310).
The "master_clock_rate" is the rate at which samples are passed between FPGA and the RF front end (In the case of B210 and E310 that RF fronted is an RFIC that contains analog RF circuits, converters and DSP).
The reason that they can be different is that the FPGA contains substantial digital filtering thats allows integer ratio decimation/interpolation and digital tuning.
Historically older USRP's had a fixed master_clock_rate (It was simply the clock that drove the DAC's and ADC's) and so most user API interaction was via programming the "sample rate", newer USRP's have the additional flexibility of configurable "master clock rates" also.

In the case of your example, yes, a suitable configuration for working with LTE signals would be to program both sample_rate and master_clock_rate to 30.72MHz.

-Ian

On Jul 23, 2015, at 8:13 AM, Crozzoli Maurizio via USRP-users <usrp-users at lists.ettus.com<mailto:usrp-users at lists.ettus.com>> wrote:


The question is: could anyone explain the relationship between the two ratesd in the subject?

To be more specific, working with LTE signal in the RX side I might need to set e.g. a sampling rate of 30.72 Msps. For doing that, I would think to use the set_rx_rate command. But then I happen to read in the archives of our mailing list (on February 2015, "Question on set_rx_bandwidth") a comment by Marcus Leech who says that "Whatever sample-rate you pick *MUST* be an integer fraction of the master-clock rate, which by default if you don't set it, is 32MHz.  There is no fractional resampling done in the hardware.".
So I would say that, according to what is needed in my example given above, I'd set also the master clock rate of the board before setting the rx (sampling) rate:
set_master_clock_rate = 30.72e6
set_rx_rate = 30.72e6

Is it correct?

Any further comments on the subject I'd better be informed of (e.g. about setting also the RX bandwidth)?

Please, if you can answer my question, specifically refer to B210 and E310 boards if needed, which the ones we have.

TIA!

BR,
Maurizio Crozzoli.

- Reference links:
- https://www.ettus.com/product/details/USRP-E312
- http://lists.ettus.com/pipermail/usrp-users_lists.ettus.com/2015-July/015109.html
