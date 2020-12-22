# Parametrically Generated 3D Printable ABLOY Keys

<p align="center">
   <img src="https://pub.trosa.io/abloy_openscad.png"/><br>
</p>

Inspired by [Dave Pedu's 3D printed Kwikset keys](https://hackaday.io/project/27631-3d-printing-real-world-keys) and
that the patents for the ABLOY PROTEC keys were set to expire in a couple of weeks, this OpenSCAD model generates keys
for the ABLOY PROTEC line of locks.

## 3D Printing

Functional keys have been produced from this model printed using an Anycubic Photon resin-based printer.

The models generated by this library are designed to allow printing flat on the bed with no supports.
With some combinations of tip cuts or bitting reorienting the model or using some supports may be required however.

FDM printers are unlikely to have sufficient accuracy to print a functional key, but I would be interested in hearing
if someone manages to with a non-SLA/DLP printer!

## Usage

The easiest way to use this is to create a new `.scad` file that uses the desired library.

### Disklock ®

<img src="http://lockwiki.com/images/4/4e/Abloy_Disklock_key_bitting.jpg" width="100">

```scad
use <disklock.scad>

disclock([0,6,1,4,2,3,1,0,5,2],tip_cuts=[0],label="Sample");
```

The `tip_cuts` list indicates which sections of the tips should have warding cut out and ranges from 0 to 6.
Alternative the `tip_cut_all` flag can be set to true to generate a modified tip that should work in most if not all
locks.

The `dss_dimples` list indicates what positions dimples for the Disc Steering System should be at, normally 9 or 11
matching how many cuts your key has. These are usually for cam locks and pad locks.

The `dc_dimple` flag controls if the Disc Controller dimple should be cut out. This is usually for door locks.

### Protec ®

<img src="http://lockwiki.com/images/0/03/Abloy_Protec_key_bitting.jpg" width="100">

```scad
use <protec.scad>

protec([0,6,1,4,2,3,1,0,5,2,3],tip_cuts=[0],dss_dimples=[11],dc_dimple=true,label="Fig. 11");
```

The `tip_cuts` list indicates which sections of the tips should have warding cut out and ranges from 0 to 6.
Alternative the `tip_cut_all` flag can be set to true to generate a modified tip that should work in most if not all
locks.

The `dss_dimples` list indicates what positions dimples for the Disc Steering System should be at, normally 9 or 11
matching how many cuts your key has. These are usually for cam locks and pad locks.

The `dc_dimple` flag controls if the Disc Controller dimple should be cut out. This is usually for door locks.

### Protec 2 ®

This library could be adapted for PROTEC 2 fairly easily, although I suspect an appropriately sized  metal ball bearing
retained with a separately printed plug would be required for best results.

If anyone experiments with this or wants to send me a PROTEC 2 core to play with I'd love to hear from you.

## References

* [Lockwiki](http://lockwiki.com) LockWiki
  * [Disklock](http://lockwiki.com/index.php/Abloy_Disklock)
  * [Protec](http://lockwiki.com/index.php/Abloy_Protec)
* [Toool](https://toool.nl/) Evolution of Abloy series
  * [Abloy Classic](https://toool.nl/images/5/58/Abloy.pdf)
  * [Abloy Disklock](https://toool.nl/images/f/f3/Abloypart2.pdf)
  * [Abloy Protec](https://toool.nl/images/8/8a/Abloypart3.pdf)
* [Abloy Protec Patent US6799447B2](https://patents.google.com/patent/US6799447B2)
* [ProtecVol Abloy](http://protectvol.online.fr/abloy.html)
