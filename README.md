smeterd
=======

Cloned from the original version by nrocco (thanks!): https://github.com/nrocco/smeterd 

Read P1 smart meter packets in Python

[Supported meters](supported-meters.md)

installation
------------

`smeterd` is fully python 3.6+ compatible.

It is highly recommended to use virtualenv for this.
After having your virtualenv installed and activated run the following command to install
the `smeterd` package directly from pypi (using pip):

    $ pip install smeterd

building
-----------------------

If you want to edit the sources, you can clone the smeterd repo, edit, build and install.

Make sure you have git, python3 and build installed.
On my Raspberry Pi W Zero I had to install (note: might not be the best way, but it worked):

    $ sudo apt-get update
    $ sudo apt-get upgrade
    $ sudo apt install git
    $ sudo apt-get install python3
    $ sudo apt install python3-pip
    $ pip3 install build

Depending on your system, `python` could be linked to either python2 or python3.
Make sure it's linked to python3 (you can check with ``ls -l `which python` ``) and if not, add an alias to your ~/.bashrc or ~/.bash_aliases file: `alias python=/usr/bin/python3`.

Now clone the repo to your local system:

    $ git clone https://github.com/Ondeugd/smeterd.git
    $ cd smeterd
    
If you want to change anything; now's the time: edit the sources (make sure to update the version in your setup.cfg if building a release version).

Now build your smeterd (creates venv isolated env, installs necessary packages, build dist package) 

    $ python -m build
    $ cd dist
    $ pip3 install smeterd-2.9.2-py2.py3-none-any.whl

If you don't want to install `smeterd` as a package you can run it directly
from the root directory of the git repository using the following command 
(but you'll have to install dependencies manually):

    $ python -m smeterd



usage as a cli application
--------------------------

To get an idea of the available functionality see the `help` output:

    $ smeterd --help

To get help for a specific subcommand use the `--help` after
having typed the subcommand:

    $ smeterd {subcommand} --help
    like
    $ smeterd read-meter --help
    
Read one packet from your meter using the following command:

    $ smeterd read-meter
    Time                      2013-08-25 10:10:45.337563
    Total kWh High consumed   651038
    Total kWh Low consumed    546115
    Total gas consumed        963498
    Current kWh tariff        1
    Gas Measured At           1516562094


By default the `read-meter` commands spits out the some default measurements like 
current date, total kwh1, total gas amounts etc on multiple lines.

You can make it print the same values as a tab seperated list:

    $ smeterd read-meter --tsv
    2013-05-04 22:22:32.224929	331557	199339	749169	1	1516562094


By piping the output of the `read-meter --tsv` command to a bash script you can fully
customize what you want to do with the data:

    IFS='{tab}'
    while read date kwh1 kwh2 gas tariff gas_measured_at; do
      mysql my_database -e "INSERT INTO data VALUES ('$date', $kwh1, $kwh2, $gas, $tariff, $gas_measured_at);"
    done < /dev/stdin


Typically you run this command from `cron` every x minutes (e.g. 5 minutes):

    */5 * * * * /path/to/venv/bin/smeterd read-meter | save_to_mysql_script.sh


If you need to use another serial port then the default `/dev/ttyUSB0` you can
use the above command with the `--serial-port` option:

    $ smeterd read-meter --serial-port /dev/ttyS0


If you specify the `--raw` command line option you will see the
raw packet from the smart meter (with additional measured values):

    $ smeterd read-meter --raw
    /ISk5\2ME382-1004

    0-0:96.1.1(xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx)
    1-0:1.8.1(00331.476*kWh)
    1-0:1.8.2(00199.339*kWh)
    1-0:2.8.1(00000.000*kWh)
    1-0:2.8.2(00000.000*kWh)
    0-0:96.14.0(0001)
    1-0:1.7.0(0000.13*kW)
    1-0:2.7.0(0000.00*kW)
    0-0:17.0.0(0999.00*kW)
    0-0:96.3.10(1)
    0-0:96.13.1()
    0-0:96.13.0()
    0-1:24.1.0(3)
    0-1:96.1.0(xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx)
    0-1:24.3.0(130504210000)(00)(60)(1)(0-1:24.2.1)(m3)
    (00749.123)
    0-1:24.4.0(1)
    !


usage as a python module
------------------------

If using `smeterd` as a cli application you will find that its functionality
is quite limited. You can use the `smeterd` package as a regular python module
so you can integrate the reading of P1 packets into your own solutions.

First initiate a new SmartMeter object:
```python
from smeterd.meter import SmartMeter
meter = SmartMeter('/dev/ttyS0')
```

Now to read one packet from the meter:
```python
packet = meter.read_one_packet()
print(packet)
print(packet['instantaneous']['l1']['volts'])
```

Do not forget to close the connection to the serial port:
```python
meter.disconnect()
```

The `SmartMeter.meter.read_one_packet()` function will return an instance of
the `smeterd.meter.P1Packet` class.


contribute
----------

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Make sure that tests pass (`make test`)
5. Push to the branch (`git push origin my-new-feature`)
6. Create new Pull Request

standards
---------

The P1 port is described in the `P1 companion standard / Dutch Smart Meter Requirements` published by *Netbeheer Nederland* (association of the Netherlands' energy network operators):  
https://www.netbeheernederland.nl/_upload/Files/Slimme_meter_15_a727fce1f1.pdf

The dataformat is described in `IEC 62056-21 (Electrical metering-Data exchange for meter reading, tariff and load control – Part 21: direct local data exchange, 2002-05)`.
