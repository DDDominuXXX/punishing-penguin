# Punishing Penguin

Convert Kubuntu into a *"rolling release"* that tracks the `devel` series; forked form wimpysworld/rolling-rhino.

<h1 align="center">
  <img src="DDDominuXXX_logo.svg" alt="DDDominuXXX" />
  <br />
  Punishing Penguin
</h1>

<p align="center"><b>Simple shell script to make Kubuntu/Ubuntu Studio track the `devel` series.</b></p>
<p align="center">Made with 💝 for <img src=".github/ubuntu.png" align="top" width="18" /> (and derivatives).</p>

## Introduction

Punishing Penguin is a simple tool to convert Ubuntu Desktop, and the official
desktop flavours, that has been installed from a daily image into a
*"rolling release"* by opting into and tracking the `devel` series.

Punishing is intended for Ubuntu developers and experienced Ubuntu users
who want to install Ubuntu once and the track all development updates with
automatic tracking of subsequent series.

Discord for Rolling Rhino (project from which this was forked): [![Discord](https://img.shields.io/discord/712850672223125565?color=0C306A&label=WimpysWorld%20Discord&logo=Discord&logoColor=ffffff&style=flat-square)](https://discord.gg/DrQgYMf)

## Caveats

If you use Punishing Penguin to opt-in to `devel` series you're assuming support
of your system, including taking care of PPA migrations, cleaning
obsolete/orphaned packages and **actively participating in any issue resolution
for problems you may encounter** via [Launchpad](https://launchpad.net) using
tools such as `apport` and `ubuntu-bug`.

You will see `W: Conflicting distribution:` warnings from `apt` as its
configuration will now reference the `devel` series which is a pointer to the
current in-development series. But they are just that, warnings.

### Origins of Rolling Rhino

[Ubuntu Podcast](https://ubuntupodcast.org) had feedback about making Ubuntu
a rolling release, something they discussed during the main segment of
[S13E12 - Red Sky in the Morning](https://ubuntupodcast.org/2020/06/11/s13e12-red-sky-in-the-morning/)
and then covered again based on listener feedback during
[S13E14 - Ace of Spades](https://ubuntupodcast.org/2020/06/25/s13e14-ace-of-spades/).
During episode S13E14 guest presenter [Stuart Langridge](https://twitter.com/sil)
proposed *"Ubuntu Rolling Rhino"* as the name for a rolling Ubuntu release
along with some ideas as to how it could be implemented. [Sergio Schvezov](https://twitter.com/sergiusens) then
[followed up via Twitter reminding us that the `devel` series exists in Ubuntu](https://twitter.com/sergiusens/status/1276479711372292096).
This inspired Martin Wimpress to create this `rolling-rhino` tool to somewhat implement
Stuart's idea by taking advantage of the `devel` series.

### Where it all came together

See the video where Martin Wimpress worked with the community to put together the initial implementation of `rolling-rhino`.

[![Making Ubuntu a rolling release - Rolling Rhino](https://img.youtube.com/vi/Q4k8LqEUxlM/0.jpg)](https://www.youtube.com/watch?v=Q4k8LqEUxlM)

## Usage

  * Install Ubuntu Desktop, or one of the desktop flavours, **from a daily image**.
    * [Ubuntu Desktop Daily Build](http://cdimage.ubuntu.com/daily-live/current/)
    * [Kubuntu Daily Build](http://cdimage.ubuntu.com/kubuntu/daily-live/current/)
    * [Lubuntu Daily Build](http://cdimage.ubuntu.com/lubuntu/daily-live/current/)
    * [Ubuntu Budgie Daily Build](http://cdimage.ubuntu.com/ubuntu-budgie/daily-live/current/)
    * [Ubuntu Kylin Daily Build](http://cdimage.ubuntu.com/ubuntukylin/daily-live/current/)
    * [Ubuntu MATE Daily Build](http://cdimage.ubuntu.com/ubuntu-mate/daily-live/current/)
    * [Ubuntu Studio Daily Build](http://cdimage.ubuntu.com/ubuntustudio/dvd/current/)
    * [Xubuntu Daily Build](http://cdimage.ubuntu.com/xubuntu/daily-live/current/)
  * Boot the new install and use `rolling-rhino` to convert it to a rolling release.

```
git clone https://github.com/DDDominuXXX/punishing-penguin.git
cd punishing-penguin
sudo ./punishing-penguin
```

Which will output something like this:

```
Punishing Penguin 🐧
  [+] INFO: lsb_release detected.
  [+] INFO: Detected dx-desktop.
  [+] INFO: No PPAs detected, this is good.
  [+] INFO: All checks passed.
Are you sure want to start tracking the devel series? [y/N]
```

## Credits
  * Thanks to [Martin Wimpress](https://twitter.com/m_wimpress) ([@wimpysworld](https://github.com/wimpysworld)) creating the original Rolling Rhino script.
  * Thanks to [Stuart Langridge](https://twitter.com/sil) for [naming the original project and proposing the idea]().
  * Thanks to [Sergio Schvezov](https://twitter.com/sergiusens) for [reminding @wimpysworld that the `devel` series exists in Ubuntu](https://twitter.com/sergiusens/status/1276479711372292096).
  * Thanks to [RickAndTired](https://twitter.com/RickAndTired) for [answering the call for help](https://twitter.com/RickAndTired/status/1276729643068911618) and [making the Rolling Rhino logo](https://github.com/RickAndTired/Artwork).

## TODO

  - [x] Detect system is running an Ubuntu Development Branch.
  - [x] Detect desktop meta packages.
  - [x] Detect PPAs.
  - [x] Detect `sources.list` is not already tracking `devel`.
  - [x] Create clean `sources.list` that tracks `devel`.
  - [ ] Use `yad` to [create a UI](https://sanana.kiev.ua/index.php/yad)
