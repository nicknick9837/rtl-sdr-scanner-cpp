# Introduction

This project contains sdr scanner written in `c++` to **scan and record multiple interesting frequencies bandwidth in the same time** (eg. 108 MHz, 144 MHz, 440 Mhz,  etc). This is possible by switching quickly between frequencies bandwidth.

Sdr scanner also allows you to record multiple transmissions simultaneously (if they are transmitted on the same band). For example, if one transmission is on 145.200 MHz and the other is on 145.600 MHz, the scanner will record and save both!

It also provides easy but very powerful **web panel** to explore recordings and spectrograms.

# Wiki

Many useful instructions and information are on the [wiki](https://github.com/shajen/rtl-sdr-scanner-cpp/wiki).

# Supported devices

Sdr scanner use [SoapySDR](https://github.com/pothosware/SoapySDR) library to get data so it support all devices that are supported by `SoapySDR`. Full list of supported devices [here](https://github.com/shajen/rtl-sdr-scanner-cpp/wiki/Supported-devices).

# Supported modulation

- `FM`
- `AM`

# YouTube

[introduction video](https://www.youtube.com/watch?v=YzQ2N0VkKvE) - thanks to **Tech Minds**!

[introduction video](http://www.youtube.com/watch?v=TSDbcb7wSjs) - old version

# Sample data collected

| Spectrogram | Transmission |
| - | - |
| ![](images/spectrograms.png?raw=1) | ![](images/transmissions.png?raw=1) |
| ![](images/spectrogram.png?raw=1) | ![](images/transmission.png?raw=1) |

# Quickstart

## Install docker

If you do not have `docker` installed, follow the instructions available at [https://docs.docker.com/desktop/](https://docs.docker.com/desktop/) to install `docker` and `docker compose`.

## Run

Download sample configuration and docker file, then run it. Customize `config.json` to your needs.
```
mkdir -p sdr
cd sdr
wget https://github.com/shajen/rtl-sdr-scanner-cpp/raw/master/config.json
wget https://github.com/shajen/rtl-sdr-scanner-cpp/raw/master/docker-compose.yml
docker compose up
```

To update docker images to latest version type:
```
docker compose pull
```

Also remember to update `docker-compose.yml` and `config.json`.

## Panel

Open [http://localhost:8000/sdr/spectrograms/](http://localhost:8000/sdr/spectrograms/) and wait for data to collect.

Admin panel available at [http://localhost:8000/admin/](http://localhost:8000/admin/). Username: `admin`, password: `password`.

# Config

Follow instruction [here](https://github.com/shajen/rtl-sdr-scanner-cpp/wiki/Configuration).

# Debugging

If you have some problems with this software follow the steps to get debug log.

Set `"console_log_level": "trace"` in `config.json`.

Then run app normally by `docker compose up`. After the error run `docker compose logs > logs.txt`. Please attach `logs.txt` if you create a new issue. Do not paste logs directly to issue. Upload it to any file host service ([https://file.io/](https://file.io/), [https://pastebin.com/](https://pastebin.com/) or any you like).

# Timezone

If timezone detection not work correctly and it seems to use `UTC` instead your timezone please set timezone in host system. To set `Europe/Warsaw` type:
```
echo "Europe/Warsaw" | sudo tee /etc/timezone
```

# Contributing

In general don't be afraid to send pull request. Use the "fork-and-pull" Git workflow.

1. **Fork** the repo
2. **Clone** the project to your own machine
3. **Commit** changes to your own branch
4. **Push** your work back up to your fork
5. Submit a **Pull request** so that we can review your changes

NOTE: Be sure to merge the **latest** from **upstream** before making a pull request!

# Donations

If you enjoy this project and want to thanks, please use follow link:

- [Revolut](https://revolut.me/borysm2b) (best way)

- [PayPal](https://www.paypal.com/donate/?hosted_button_id=6JQ963AU688QN)

# License

[![License](https://img.shields.io/:license-GPLv3-blue.svg?style=flat-square)](https://www.gnu.org/licenses/gpl.html)

- *[GPLv3 license](https://www.gnu.org/licenses/gpl.html)*
