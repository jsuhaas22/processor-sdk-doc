#################################
 Linux 12.00.00 Performance Guide
#################################

***************
Read This First
***************

**All performance numbers provided in this document are gathered using
following Evaluation Modules unless otherwise specified.**

+----------------+----------------------------------------------------------------------------------------------------------------+
| Name           | Description                                                                                                    |
+================+================================================================================================================+
| AM64x EVM      |  AM64x Evaluation Module rev E1 with ARM running at 1GHz, DDR data rate 1600 MT/S                              |
+----------------+----------------------------------------------------------------------------------------------------------------+

Table:  Evaluation Modules

*****************
About This Manual
*****************

This document provides performance data for each of the device drivers
which are part of the Processor SDK Linux package. This document should be
used in conjunction with release notes and user guides provided with the
Processor SDK Linux package for information on specific issues present
with drivers included in a particular release.

For further information or to report any problems, contact
https://e2e.ti.com/ or https://support.ti.com/

|

*****************
System Benchmarks
*****************

|

|

CRYPTO
======

.. _crypto-performance:

Crypto Performance Comparison
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The following table shows different AES/SHA algorithms throughput measured using openssl speed across the SA2UL accelerator, ARM Cryptographic Extension (CE), and baseline ARM CPU.

.. csv-table:: Crypto Accelerator Performance
   :header: "Algorithm", "Size (bytes)", "Accelerator (MB/s)", "ARM CE (MB/s)", "ARM (MB/s)"
   :widths: 20, 25, 20, 20, 20

   "aes-128-cbc", "16", "0.36", "67.74", "22.19"
   "aes-128-cbc", "64", "1.61", "212.79", "28.35"
   "aes-128-cbc", "256", "6.34", "449.47", "30.64"
   "aes-128-cbc", "1024", "19.02", "637.13", "31.25"
   "aes-128-cbc", "8192", "101.91", "727.25", "31.44"
   "aes-128-cbc", "16384", "136.80", "734.06", "31.44"
   "aes-128-ecb", "16 bytes", "0.36", "72.76", "23.15"
   "aes-128-ecb", "64 bytes", "1.62", "199.11", "28.66"
   "aes-128-ecb", "256 bytes", "6.39", "456.68", "30.60"
   "aes-128-ecb", "1024 bytes", "18.95", "685.38", "31.12"
   "aes-128-ecb", "8192 bytes", "101.67", "806.09", "31.28"
   "aes-128-ecb", "16384 bytes", "139.55", "814.81", "31.27"
   "aes-192-cbc", "16 bytes", "0.36", "66.82", "19.97"
   "aes-192-cbc", "64 bytes", "1.59", "196.38", "24.62"
   "aes-192-cbc", "256 bytes", "6.36", "376.01", "26.25"
   "aes-192-cbc", "1024 bytes", "18.88", "496.14", "26.68"
   "aes-192-cbc", "8192 bytes", "97.58", "547.43", "26.84"
   "aes-192-cbc", "16384 bytes", "130.47", "551.05", "26.71"
   "aes-192-ecb", "16 bytes", "0.37", "70.86", "21.01"
   "aes-192-ecb", "64 bytes", "1.68", "191.99", "25.32"
   "aes-192-ecb", "256 bytes", "6.67", "426.36", "26.77"
   "aes-192-ecb", "1024 bytes", "19.54", "621.73", "27.15"
   "aes-192-ecb", "8192 bytes", "101.79", "717.97", "27.27"
   "aes-192-ecb", "16384 bytes", "134.23", "725.00", "27.24"
   "aes-256-cbc", "16 bytes", "0.34", "71.41", "22.53"
   "aes-256-cbc", "64 bytes", "1.52", "211.82", "27.12"
   "aes-256-cbc", "256 bytes", "5.98", "405.04", "28.65"
   "aes-256-cbc", "1024 bytes", "18.14", "532.25", "29.18"
   "aes-256-cbc", "8192 bytes", "74.33", "566.03", "29.24"
   "aes-256-cbc", "16384 bytes", "103.42", "578.21", "29.25"
   "aes-256-ecb", "16 bytes", "0.36", "65.54", "18.39"
   "aes-256-ecb", "64 bytes", "1.62", "175.31", "21.71"
   "aes-256-ecb", "256 bytes", "6.44", "370.39", "22.80"
   "aes-256-ecb", "1024 bytes", "18.90", "535.87", "23.08"
   "aes-256-ecb", "8192 bytes", "94.67", "609.52", "23.17"
   "aes-256-ecb", "16384 bytes", "124.78", "615.11", "23.15"
   "sha2-256", "16 bytes", "0.36", "8.34", "5.37"
   "sha2-256", "64 bytes", "1.41", "30.63", "15.83"
   "sha2-256", "256 bytes", "5.61", "100.69", "35.91"
   "sha2-256", "1024 bytes", "21.55", "233.92", "52.80"
   "sha2-256", "8192 bytes", "124.61", "383.28", "61.20"
   "sha2-256", "16384 bytes", "190.61", "400.21", "61.86"
   "sha2-512", "16 bytes", "0.34", "5.15", "5.15"
   "sha2-512", "64 bytes", "1.38", "20.53", "20.52"
   "sha2-512", "256 bytes", "5.19", "44.68", "44.68"
   "sha2-512", "1024 bytes", "17.93", "75.68", "75.66"
   "sha2-512", "8192 bytes", "61.53", "94.91", "94.83"
   "sha2-512", "16384 bytes", "74.50", "96.57", "96.52"

.. csv-table:: CPU Usage %
   :header: "Algorithm", "Accelerator (%)", "ARM CE (%)", "ARM (%)"
   :widths: 25, 25, 25, 25

   "aes-128-cbc", "38%", "99%", "99%"
   "aes-128-ecb", "38%", "99%", "99%"
   "aes-192-cbc", "38%", "99%", "99%"
   "aes-192-ecb", "38%", "99%", "99%"
   "aes-256-cbc", "38%", "99%", "99%"
   "aes-256-ecb", "38%", "99%", "99%"
   "sha2-256", "90%", "99%", "99%"
   "sha2-512", "91%", "99%", "99%"
