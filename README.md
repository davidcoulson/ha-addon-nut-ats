# NUT add-on with the APC ATS output patch

A copy of the [Home Assistant Community NUT add-on](https://github.com/hassio-addons/addon-nut) v0.18.1 (NUT 2.8.5)
with one extra patch, `nut_ats/patches/0002-apc-ats-output-phase-table.patch`, from
[networkupstools/nut#3763](https://github.com/networkupstools/nut/pull/3763). The patch makes the `snmp-ups` `apc_ats`
subdriver publish `output.current`, `output.voltage`, `ups.power` and `ups.load` from the ATS output phase table
(for example on the APC AP4452A).

Home Assistant builds the add-on locally from the Dockerfile (there is no prebuilt image). Add this repository in
Settings > Add-ons > Add-on store > Repositories, then install "Network UPS Tools (ATS patch)". Its options are the
same as the upstream add-on's. It can run next to the upstream add-on as long as the two don't share a USB device.

Drop it once the patch is in a NUT release that the upstream add-on ships.
