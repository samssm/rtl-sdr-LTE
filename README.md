rtl-sdr-LTE
===========

Play with LTE signal captured by rtl-sdr.

By a enthusiast <putaoshu@msn.com> <putaoshu@gmail.com> of Software Defined Radio.

Some files are borrowed from https://github.com/Evrytania/LTE-Cell-Scanner, https://github.com/Evrytania/Matlab-Library and https://github.com/JiaoXianjun/multi-rtl-sdr-calibration

As China has announced TD-LTE deployment officially, I want to decode it with LTE-Cell-Scanner (written by James Peroulas: https://github.com/Evrytania/LTE-Cell-Scanner).

Then there are some discoveries:

Frequencies of LTE in China are discovered by searching in internet:

FDD band:

China Mobile:  1880-1900MHz (maybe it is also TDD)

China telecom: 1755-1785MHZ(uplink)/1850-1880MHz(downlink)

China unicom:  1955-1980MHz(uplink)/2145-2170MHz(downlink)

TDD band:

China Mobile:  2575-2635 MHz

China telecom: 2635-2655 MHz

China unicom:  2555-2575 MHz

Then those bands are scanned with my MATLAB scanner: https://github.com/JiaoXianjun/multi-rtl-sdr-calibration (see README_for_spectrum_scanner.txt in that repo. Or just search rtl-sdr in http://www.mathworks.com/matlabcentral/fileexchange/)

See those .png files for spectrum plots. (For the band above 2.5GHz which has exceeded range of rtl-sdr dongle, a MMDS LNB is used to extend the band to above 2.5GHz. 
See MMDS-LNB-LO1998-to-extend-dongle-band.jpg. I learn this method from http://blog.cyberexplorer.me/2014/01/sniffing-and-decoding-nrf24l01-and.html and https://github.com/omriiluz/NRF24-BTLE-Decoder. 
The LO of my LNB is 1998MHz. It means that when the dongle is tuned to 600MHz, it actually receives 600+1998Mhz!)

LTE-Cell-Scanner decodes LTE MIB successfully in 1850-1880MHz band, but unsuccessful for other bands even they seems pretty like LTE 20MHz spectrum.

I think it maybe because relative time location of PSS and SSS is different in TDD from FDD. It is confirmed with James Peroulas.

Inspired by James Peroulas, initial exploration with only PSS correlation is done on captured IQ data, and valid PSS has been seen there! (Try it with matlab/test_td_lte_pss.m)

Now TD-LTE signal is identified successfully, maybe adding TD-LTE support to LTE-Cell-Scanner is a good idea.

Please join me if you are also interested in this. Please see TODO firstly.

News
=======================
2014-01-07:

PSS has been detected successfully at frequency 2645MHz! See comments in matlab/test_td_lte_pss.m, and then run it.

Usage
=======================
2014-01-07:

See comments in matlab/test_td_lte_pss.m, and then run it. PSS has been detected successfully at frequency 2645MHz!

Contributing
=======================
You are welcome to send pull requests in order to improve the project.

See TODO list included in the source distribution first (If you want).


