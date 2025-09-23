L-INX - Automation Server 8.4.4
===============================================================================

Version String: 2025-08-22 10:13:00 - V8.4.4

LINX-xxx are LOYTEC products (www.loytec.com)
-------------------------------------------------------------------------------

!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!! ATTENTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

With firmware 7.0, the handling of binary values in Java scripts has been 
changed and existing code must be adjusted. In older versions, binary data was 
exchanged as a string, now this data is handled as binary JSON. For example
old code:
  if(value[0] == 'TRUE') { }
now must be adapted to new code: 
  if(value[0] == true) { }
  
Also the invalid value was updated to be a JSON null instead of a string "--".



1 Notes and Requirements
========================

This firmware can only be used with the following products:
+ LINX-102, LINX-103
+ LINX-112, LINX-113
+ LINX-120, LINX-121
+ LINX-150, LINX-151, LINX-153, LINX-154
+ LINX-202, LINX-203
+ LINX-212, LINX-213, LINX-215
+ LINX-220, LINX-221


2 Archive Contents
==================

File name                                 Description
-------------------------------------------------------------------------------
LINX_Readme.txt                           this file
-------------------------------------------------------------------------------
linx_lgate_lroc_liob_ldali_lipme_8_4_4.zip   image archive for firmware upgrade
-------------------------------------------------------------------------------


3 Installation
==============


3.1) Firmware upgrade via L-INX Configurator (via Ethernet)
----------------------------------------------------------

Please see the L-INX/L-GATE User Manual on how to upgrade the firmware on L-INX,
L-GATE devices via Web service connection using the L-INX Configurator software. 
The L-INX/L-GATE User Manual and the L-INX Configurator software
are available via the LOYTEC Web site (http:\\www.loytec.com\).

3.2) Firmware upgrade on the Web UI (via Ethernet)
--------------------------------------------------

Please see the respective User Manual on how to upgrade the firmware
using the Web UI of the LOYTEC device (Config -> Firmware). 
The L-INX/L-GATE User Manual is available via the LOYTEC Web site
(http:\\www.loytec.com\).


4 Changes to previous releases
==============================

LINX-102/103/112/113/120/121/150/151/153/154 8.4.4 (2025-08-22)
LINX-202/203/212/213/215/220/221             8.4.4 (2025-08-22)
---------------------------------------------------------------

+ Fixed BACnet "out of resources" error when using the higher PLC BACnet limit. 
+ Fixed node.js certificate that got deleted after clearing the configuration.
+ MP-Bus now shows a warning, if devices are commissioned on an interface that 
  is not connected.
+ Fixed update of Status_Flags_OVERRIDDEN when overriding a data point on the 
  Web UI.
+ Improved node.js data point service under high load.

LINX-102/103/112/113/120/121/150/151/153/154 8.4.2 (2025-08-01)
LINX-202/203/212/213/215/220/221             8.4.2 (2025-08-01)
---------------------------------------------------------------

+ Fixed LIOB-FT upgrade progress display for Configurator.
+ Fixed crash on L-IOB Web UI during remote L-IOB firmware upgrade.
+ Fixed restoring to default gateway after recovering from failover interface.
+ Fixed value propagation between unlinked favorites over local connection. 
+ Improved LTE-800 authentication if device disconnects mid-process.
+ Fixed crash in SMI stack after some time.
+ Fixed receiving KNX frames for a comm object with zero (unknown) length.
+ Fixed permanently disconnected LRS232-802 after EMI.
+ Security hardening for EN-18031-1.
+ Security update: OpenSSL 3.4.2.

LINX-102/103/112/113/120/121/150/151/153/154 8.4.0 (2025-05-21)
LINX-202/203/212/213/215/220/221             8.4.0 (2025-05-21)
---------------------------------------------------------------

+ Allow discovering LOYTEC devices at loytec.local.
+ Make Web UI responsive to fit better on mobile devices.
+ Option to enforce setting strong passwords.
+ Device is locked down before setting a password.
+ Added "view" role that allows viewing configurations on Web UI.
+ Allow disabling built-in admin, operator accounts.
+ Allow configuring anonymized login landing page on Web UI.
+ Allow changing cipher specs on Web UI.
+ Allow configuring a custom login banner for the Web UI.
+ Allow disabling global connections on Web UI.
+ Backup/restore with password option to encrypt credentials. 
+ Web UI: Added option to turn off daily firmware upgrade check.
+ Web UI: Folder view on trend overview page.
+ Web UI: Name search function in data point list.
+ Web UI: Fixed login for user names with 32 characters.
+ Show overall device status on LCD main page.
+ Support placeholder %{folder_descr} in data point description.
+ Support SMI 3.0 BF.
+ New dynamic BACnet server object limits for PLC-created objects.
+ L-IOB: Show number of overridden I/Os on device info page.
+ L-IOB: Option to generate alerts for I/Os on device info page.
+ BACnet: Description length increased to 256 characters.
+ BACnet: Fixed MS/TP token-passing if there is no node number below 104 on the 
  bus (A64 only).
+ BACnet/SC: Support uploading CA certificate chain.
+ BACnet/SC: Support decoded Wireshark log.
+ BACnet/SC: Support IPv6.
+ BACnet/SC: Support certificate Web service for on-boarding.
+ OPC UA: Save the last 10 untrusted client certificates.
+ OPC UA: Update of device IP addresses shall not restart the server.
+ OPC UA: Support subscription on ServerStatus and ServerStatus_CurrentTime.
+ Support site-to-site VPN.
+ Support configuring alternative backup routes.
+ L-STUDIO: Watch protocol as Web service.
+ L-STUDIO: Fixed disabling SSH via deployment of system settings.
+ EnOcean: Fixed radio conversion command sent to LENO-802.
+ dpal.js: Correctly refresh subscription IDs when a remote device reconnects.
+ Update node.js to 18.20.8.
+ Renewed default certificate and upgraded to RSA 2048.
+ Security update: OpenSSL 3.4.1, IWD 3.3, OpenVPN 2.6.14.

LINX-102/103/112/113/120/121/150/151/153/154 8.2.14 (2025-03-28)
LINX-202/203/212/213/215/220/221             8.2.14 (2025-03-28)
---------------------------------------------------------------

+ BACnet/SC: Accept HTTP 417 error code when connecting.
+ Add LTE verbose logging option in Web UI.
+ Improved Ethernet re-negotiation after link gets stalled.
+ Extend the L-IOB host statistics file with more information.
+ Fixed L-IOB host Web UI to reboot or factory reset a remote L-IOB.
+ Enhanced stability of AFT communication with remote devices.
+ Fixed writing members of overridden structured data point when it was invalid
  value.
+ OpenSSL 3.1.8 security update.

LINX-102/103/112/113/120/121/150/151/153/154 8.2.12 (2025-02-03)
LINX-202/203/212/213/215/220/221             8.2.12 (2025-02-03)
---------------------------------------------------------------

+ Support clearing historic filter data on Web UI.
+ Modbus master distributes slave online check over a time interval.
+ Fixed Modbus-TCP slave that started rejecting connections after some time.
+ Fixed Modbus L-STAT fast 100ms pollgroup stopping after 24 days.
+ Fixed system time register stopping after 24 days.
+ Fixed modulo math operation not working for values larger than 2^31.
+ Preset names and upcoming time properties for iCalendar schedules not working
  correctly.
+ Fixed BACnet alarm client mappings causing a memory leak.
+ BACnet/SC: Support uploading private key via separate file.
+ BACnet/SC: Fix crash when the hub closes the websocket connection unexpectedly.
+ L-STUDIO: Support watch service over websocket.
+ L-STUDIO: Fixed issue with wrong datapoint to logic variable mappings if the 
  instance table is corrupt.
+ IEC-61131 runtime: Fixed updating data points if the total variable data size 
  of a PGM block exceeded certain limits.
+ dpal-js: Fixed COV update when browsing a folder.
+ Node-RED(TM): Fixed 100% CPU load in case of unexpected crash.
+ Fixed deploy of E-Mail credentials onto device with empty credentials.
+ Fixed EnOcean L-STATs hanging in configuration state on high system load.
+ Fixed re-enabling USB port after EMI for LSMI-804, LMPBUS-804.
+ Fixed rare loss of Ethernet connectivity on A64 models.
+ OPC UA Server: Fixed writing to unlinked string favorite data points.
+ Update pre-installed LWEB-802 application to version 4.6.12
+ Security update: OpenSSL 3.1.7, Dropbear 2024.86.

LINX-102/103/112/113/120/121/150/151/153/154 8.2.10 (2024-10-23)
LINX-202/203/212/213/215/220/221             8.2.10 (2024-10-23)
---------------------------------------------------------------

+ Support UDMI client script version 2.2.0.
+ Updated Node-RED(TM) to 3.1.8.
+ OPC UA Server: Fixed issue with HistoryRead requests with 
  NumValuesPerNode >= 0x80000000.
+ OPC UA Server: Fixed finding trended favorite data points.
+ Fixed SMI power relay to be open if power-on function is deactivated.
+ Fixed relinquishing L-IOB native BACnet objects via priority write data points.
+ Fixed SMI scan if short address 0 is not the last assigned address.
+ Fixed Modbus master device retries setting to take effect.
+ Fixed writing persistent L-IOB output value to L-IOB devices after deployment.
+ Security fix for CSRF vulnerability on Web UI.

LINX-102/103/112/113/120/121/150/151/153/154 8.2.8 (2024-08-23)
LINX-202/203/212/213/215/220/221             8.2.8 (2024-08-23)
---------------------------------------------------------------

+ Improved loading the trend overview page, if it displays a large number of 
  remote trends.
+ Support M-Bus conversion non-conforming year in type F date/time format.
+ BACnet/SC improved scanning time of objects.
+ Fixed crash in BACnet alarm client due to invalid device object cache.
+ Fixed BACnet native output data points that relinquished after a reboot.
+ Fixed Ethernet network port isolation issue on A64.
+ Fixed EnOcean teach-in for devices that only contain CO with type "bidirPost". 
+ Fixed detection of EnOcean L-STAT, if another L-TAT on different port has same 
  Modbus address. 
+ Fixed MP-Bus communication that could stall after some time.
+ Fixed Modbus polling of COIL registers that may lead to incorrect values if 
  background polling is active.
+ Fixed logging offline-to-online transition in generic COV trends.
+ Fixed dynamic polling of structured NV, if a pollgroup on a member point is 
  cancelled.
+ Fixed scheduling of dateRange by generic scheduler if no endDate is specified.
+ Improved reliability of USB connected devices after excessive EMI reconnects.
+ OPC UA Server: Fixed possible infinite loop when creating OPC UA TrendLog 
  objects on A64.
+ Fixed IEC-61131 variable default value initialization issue (A64 only).
+ IEC-61131 runtime: Fixed problem that IO driver did not output PLC_OUT 
  variables in the first cycle if they their initial value was zero or false.
+ IEC-61499 runtime: Fixed problem that master state for communication module 
  with moduleId 1 was not calculated correctly.
+ IEC-61499 runtime: Added event tracing commands for performance profiling.
+ Node-RED: Improved CoV feature to work even if readDP is in a subflow. 
+ Node-RED: Fixed always overwriting topic of readDP-node with the data point 
  path.
+ Update to inadyn v1.12.0 that fixes a regression for some DynDNS providers.
+ Encrypt SMTP client credentials on device (CVE-2023-46386, CVE-2023-46388).
+ Linux patch to fix CVE-2024-1086.
+ Security updates: OpenSSL 3.1.6, OpenVPN 2.6.12.

LINX-102/103/112/113/120/121/150/151/153/154 8.2.6 (2024-05-23)
LINX-202/203/212/213/215/220/221             8.2.6 (2024-05-23)
---------------------------------------------------------------

+ Support D2-10-30 EnOcean profile.
+ Fixed enabling/disabling of EnOcean filters on protocol analyzer page. 
+ Fixed scanning of WLAN SSIDs that contain a colon.
+ Fixed possible deadlock during SMI drive direction update.
+ Fixed IEC-61131 code generation issue which calculated wrong data offsets in 
  complex POUs using large data items, like strings in structures. This could 
  lead to incomplete or wrong execution of the affected POU.
+ Fixed packet size calculation in SERIALIZECLIENT communication.
+ Updated pre-installed LWEB-802 package to version 4.6.10.
+ Security update: Dropbear v2024.84 (CVE-2023-48795, Terrapin vulnerability).

LINX-102/103/112/113/120/121/150/151/153/154 8.2.4 (2024-03-19)
LINX-202/203/212/213/215/220/221             8.2.4 (2024-03-19)
---------------------------------------------------------------

+ Fixed M-Bus device scan executed over the Configurator (A64 devices).
+ LMPBUS-804 reconnects on USB no longer trigger fault alarms.
+ L-IOB: Allow to set PulseCountInit on Web UI.
+ L-IOB: Added short detection on analog resistance inputs.
+ Mobile network warning removed if only GSM is activated.
+ Fixed expansion of %{descr} alarm placeholder on linked favorites.
+ dpal.js: Fixed cleared preset data when writing the scheduler.

LINX-102/103/112/113/120/121/150/151/153/154 8.2.2 (2024-03-01)
LINX-202/203/212/213/215/220/221             8.2.2 (2024-03-01)
---------------------------------------------------------------

+ Support changing ports of commissioned MP-Bus devices on commission Web UI.
+ Support disabling IPv6 on device.
+ Added periodic re-sync for the remote BACnet alarm summary.
+ Added path info to data points in trend CSV.
+ Updated pre-installed LWEB-802 package to version 4.6.6.
+ Fixed BACnet alarm messages with Chinese characters.
+ Support BACnet network unit conversion for client mappings.
+ Fixed update of Limit_Enable sub-data points after writing to the property.
+ Fixed update of Present_Value_ActivePriority feedback data point after 
  editing priority array on Web UI.
+ Fixed stalled Modbus RTU communication in rare cases.
+ Fixed M-Bus secondary scan crash if multiple devices found with secondary 
  address starting with 9.
+ Fixed detection of LENO-80x (broken in 8.2.0).
+ L-IOB: Increased the resolution of Override/Default/ManualValue in percentage
  mode.
+ Fixed spurious alarm e-mails by OPC remote alarm server.
+ OPC UA Server: Fixed TranslateBrowsePathsToNodeIds returning invalid NodeId.
+ OPC UA Server: Fixed possible undefined behavior when subscription lifetime 
  ends.
+ Fixed dpal-js alarm time stamps on devices with time zone.
+ Fixed dpal-js scheduler write with empty exception schedule.
+ Fixed dpal-js subscription to entire Alarm folders.
+ Fixed dpal-js reading/COV updates of large string values (>32K).
+ Fixed occasional Node-RED start problem.
+ OpenSSL 3.1.5 security update.

LINX-102/103/112/113/120/121/150/151/153/154 8.2.0 (2023-12-01)
LINX-202/203/212/213/215/220/221             8.2.0 (2023-12-01)
---------------------------------------------------------------

+ Support A64 models.
+ Allow modifying BACnet priority array on data point Web UI.
+ Allow writing to LogiCAD's PLC-out data points from other sources again.
+ New generic trend mode "interval+COV".
+ LCD UI option to save alarm log on USB storage.
+ Fixed OPC UA server memory leak for EventNotifier CreateMonitoredItems 
  requests with EventFilter. 
+ Fixed data point status updates of LIOB-110/112 data points.
+ L-IOB native BACnet input data point value now reflects the active L-IOB 
  override value.
+ Fixed L-IOB output that was out-of-sync with native BACnet point after 
  manual value.
+ Support custom FTDI USB interfaces in Node-RED.
+ Fixed dpal.js subscription COV updates with children and/or COV delta.
+ EnOcean PA adds check box to deactivate ID filter.
+ Support japanese EnOcean L-STAT models.
+ Support EC key in certificate signing request.
+ Security update: OpenSSL 3.1.4, OpenVPN 2.6.8, lighttpd 1.4.71.

LINX-102/103/112/113/120/121/150/151/153/154 8.0.8 (2023-10-18)
LINX-202/203/212/213/215/220/221             8.0.8 (2023-10-18)
---------------------------------------------------------------

+ Fixed L-IOB input value that could be wrong, if terminal is pulled to GND 
  during start-up.
+ Node-RED: Include All Sub-Folders for Subscriptions.
+ MP-Bus: Corrected transmission of data point value to MP-Bus actuator.
+ Fixed crash when writing to data point using simpleType with invalid startBit.

LINX-102/103/112/113/120/121/150/151/153/154 8.0.6 (2023-09-22)
LINX-202/203/212/213/215/220/221             8.0.6 (2023-09-22)
---------------------------------------------------------------

+ Updated pre-installed LWEB-802 package to version 4.6.4.
+ Fixed removing override from structure sub-data point to restore application 
  value.
+ Fixed dpal-js subscribeAll options used by MQTT script.
+ OpenSSL 1.1.1w security update.

LINX-102/103/112/113/120/121/150/151/153/154 8.0.4 (2023-08-21)
LINX-202/203/212/213/215/220/221             8.0.4 (2023-08-21)
---------------------------------------------------------------

+ Enhanced BACnet/SC error detail for certificates and hub connection.
+ Updated pre-installed LWEB-802 package to version 4.6.2.
+ Fixed UINT32 simple type conversion that was truncated to 2147483647.
+ Fixed BACnet change-of-reliability notifications for fault alarms.
+ Fixed LMPBUS-804 serial communication that stopped working.
+ Fixed saving the SIM PIN code after editing on the Web UI.
+ Fixed sending test SMS over local LTE-800.
+ Fixed saving scheduler binary preset values that were reset to "false" .
+ Fixed alarm placeholder %{fx} for BACnet alarms.
+ Fixed "Remove all override values" on the Web UI that could lock the device.
+ OpenSSL 1.1.1v security update.

LINX-102/103/112/113/120/121/150/151/153/154 8.0.2 (2023-05-16)
LINX-202/203/212/213/215/220/221             8.0.2 (2023-05-16)
---------------------------------------------------------------

+ Support iCalendar scheduler.
+ Web UI scheduler preset color picker.
+ Support BACnet/SC.
+ Updated WLAN configuration tabs and system registers.
+ Added pagination and scroll-to-top on Web UI.
+ Added SMS test button on Web UI.
+ Support falling/rising edge trend triggers.
+ Support path component placeholders in alarm messages.
+ Support receive timeout on unlinked favorites.
+ Support writing individual array elements via parameter file.
+ Overridden data points warning is now reflected in Status Summary register.
+ Display IP address in Modbus TCP protocol log.
+ Fixed Modbus online register test over Modbus TCP.
+ Support Modbus TCP port numbers per slave device.
+ Allow duplicate Modbus RTU addresses on commission page.
+ Allow writing BACnet OVERRIDDEN flag in a gateway use case.
+ Fixed unspecified BACnet Min_Pres_Value to read -inf.
+ EnOcean: Do not abort teach-in if message type does not match.
+ Fixed MP-Bus watchdog when reading initial data point values during startup.
+ Improved M-Bus secondary address scan.
+ M-Bus update secondary addresses of devices in configuration after performing 
  a scan.
+ M-Bus commission Web UI supports changing primary address in device list.
+ Fixed L-IOB native BACnet object reliability if L-IOB device goes offline.
+ Fixed L-IOB native BACnet object update by poll-on-startup values.
+ Fixed L-IOB native BACnet object Polarity property in analog threshold mode.
+ Fixed possible ASSERT after DST change.
+ Fixed authentication and retry issue with FreeDNS.
+ Support Google UDMI 1.4.
+ Script API for alarms, trends, schedulers.
+ Script update: node.js 18.7.0 and Node-RED 3.0.2.
+ Node-RED: Fixed dpRead value output format when reading entire folder.
+ Configure OpenVPN client from USB stick.
+ Support WLAN ports for OpenVPN local subnet router.
+ Support device certificate with EC key.
+ Updated pre-installed LWEB-802 package to version 4.6.0.
+ Security update: Run SNMP as non-root, Linux 5.10.153.

LINX-102/103/112/113/120/121/150/151/153/154 7.6.14 (2023-02-23)
LINX-202/203/212/213/215/220/221             7.6.14 (2023-02-23)
---------------------------------------------------------------

+ Support "%" character when changing passwords.
+ Fixed display of string content with control characters in data point Web UI.
+ Fixed Modbus polling when activating a register in a special configuration.
+ BACnet LOOP parameter properties no longer cleared after config deployment.
+ BACnet: Fixed memory leak when freeing client maps using COV subscriptions. 
+ BACnet: Fixed crash on processing Status_Flags of COV notifications. 
+ BACnet: Corrected msgHigh alarm text if persistent and msgLow missing.
+ Fixed acknowledgement of inactive, not acknowledged BACnet alarm after 
  re-enabling alarm condition.
+ Fixed writing to L-IOB PulseCountInit DP may not actually reset pulse count.
+ Fixed missing OPC UA data change notification for status-only changes.
+ OPC UA Server: Fixed possible overflow when creating a subscription group.
+ Fixed OPC UA subscription when adding Monitored Items with Monitoring Mode 
  other than Reporting.
+ Fixed EnOcean L-STAT failure to configure after device reboot.
+ OpenSSL 1.1.1t security update.

LINX-102/103/112/113/120/121/150/151/153/154 7.6.12 (2022-12-09)
LINX-202/203/212/213/215/220/221             7.6.12 (2022-12-09)
---------------------------------------------------------------

+ Allow manual log-off on LCD display.
+ Added new data point browser on LCD display w/o PIN protection.
+ Support M-Bus meters that respond with different data depending on FCB bit.
+ Fixed random MAC address that may show briefly when in separate network mode.
+ L-IOB native BACnet updates fixed on transitions between Manual and 
  Disabled mode.
+ L-IOB native BACnet objects: Fixed Present_Value that applied to priority 16 
  after some time.
+ Fixed script permission problems introduced in 7.6.10: read trend CSVs,
  write to /srv/www/documentation, use device certificate in HTTPS connections.
+ Fixed crash if LTE network operator does not provide its name.
+ Fixed SMI stop command that could lead to incorrect angle calculation.
+ Fixed rare restarts due to DMA kernel problem.
+ OpenSSL 1.1.1s security update.


LINX-102/103/112/113/120/121/150/151/153/154 7.6.10 (2022-10-03)
LINX-202/203/212/213/215/220/221             7.6.10 (2022-10-03)
---------------------------------------------------------------

+ L-STUDIO LROC: The number of LROC segments is now correctly decoded.
  THE RUNTIME WILL NOT START WHEN MORE SEGMENTS THAN LICENSED ARE INSTANTIATED
  IN THE PROJECT.
+ L-STUDIO LROC: An issue was fixed when a segment contained two zones of the
  same zone type that were configured quickly (e.g. due to a parameter download).
  In this case both zones got master state and aggregation functions did not
  work properly.
+ L-STUDIO LROC: A race condition was fixed when multiple zones in a room were
  triggered with a This-Room address. The race condition cancelled an update 
  that led to zones that did not follow the room command.
+ L-STUDIO IEC-61131 Runtime: The I/O driver was improved to ignore COV updates 
  on PLC_OUT variables. This solves a performance problem due to rounding 
  problems with BACnet data points, as data points use double precision while 
  BACnet analog values use single precision.
+ L-STUDIO IEC-61131 Runtime: The SPLIT_DATE function mis-calculated its output
  variables by one day for negative time zone offsets.
+ L-STUDIO IEC-61131 Runtime: The MID function output was corrupted when the 
  position input was larger than the input string length.
+ L-STUDIO IEC-61499 Runtime: The MIPGET block values "Project.StudioVersion",
  "Project.StartTime" and "Software.Version" were empty.
+ Exclude OpenVPN configuration from restore if "Restore IP configuration" is 
  disabled.
+ Make POST file transfer robust against network problems.
+ Security improvement: run node.js process as restricted script user.
+ Fixed serial driver module for node.js scripts.  
+ Fixed EVENT_INVOKE queue errors for OPC polls having >128 subscription handles.
+ Fixed OPC UA memory leak with some Subscription/Monitored items parameters.
+ Fixed SSDP memory leak when sending single UDP replies.
+ Fixed lost password of created users after firmware update.
+ Corrected PIN level for L-WEB graphics of created users with operator role.
+ Fixed M-Bus send FCB bit toggle for non-multitel messages.
+ Improved MP-Bus PPX scan to find all devices if they have no assigned address.
+ Fixed SMI driver that stopped sending movement commands after errors in bus 
  communication.
+ SMI: increase slave answer timeout to 150ms, master send delay to 20ms, 
  max retries to 10.

LINX-102/103/112/113/120/121/150/151/153/154 7.6.8 (2022-08-05)
LINX-202/203/212/213/215/220/221             7.6.8 (2022-08-05)
---------------------------------------------------------------

+ Fixed issue with OPC UA subscription keep alive (since 7.6.6).
+ Fixed sporadic system crash.

LINX-102/103/112/113/120/121/150/151/153/154 7.6.6 (2022-07-28)
LINX-202/203/212/213/215/220/221             7.6.6 (2022-07-28)
---------------------------------------------------------------

+ Fixed NTP re-sync after changing NTP servers.
+ Fixed L-IOB output to not restart PWM period when writing to it in manual mode.
+ Fixed EnOcean memory leak if send requests keep over-running the duty cycle.
+ Fixed scaling for EnOcean SoundLocalization_n90_90_R180 type.
+ Fixed vanishing SMI devices after a re-scan of the SMI channel.
+ Fixed polling fallback of "COV unsolicited + Poll" BACnet client mappings.
+ Updated pre-installed LWEB-802 package to version 4.4.4.
+ Updated node.js to 14.20.0 (CVE-2022-32214, CVE-2022-32215, CVE-2022-32222).
+ OpenSSL 1.1.1q security update.

LINX-102/103/112/113/120/121/150/151/153/154 7.6.4 (2022-06-03)
LINX-202/203/212/213/215/220/221             7.6.4 (2022-06-03)
---------------------------------------------------------------

+ M-Bus supports DIF=00 w/o VIF at the end of a frame.
+ Fixed COV BACnet trend log recording for value changes always smaller than 
  the COV increment.
+ Fixed OPC UA server stalled monitored items after multiple 
  CreateMonitoredItems requests.
+ Fixed EnOcean ID filters to be effective after a reboot.
+ Fixed MP-Bus malfunction and maintenance states.
+ Updated pre-installed LWEB-802 package to version 4.4.2.
+ Ensure LWEB-802 app is not updated if auto-update is not enabled.
+ OpenSSL 1.1.1o security update.

LINX-102/103/112/113/120/121/150/151/153/154 7.6.2 (2022-04-11)
LINX-202/203/212/213/215/220/221             7.6.2 (2022-04-11)
---------------------------------------------------------------

+ Trend preview Web UI to use step-after interpolation as a default.
+ Fixed property data point exposure in parameter XML if parent is parameter.
+ Fixed BACnet active priority and prio read data points (broken in 7.6.0).
+ EnOcean inserts minimum delay for RPS telegrams for a detectable transition.
+ Correct duplicated address info for added Modbus commission-later devices.
+ Fixed incorrect display of IP address after saving on Modbus TCP commission 
  page.
+ Fixed non-default Modbus slave register address range setting on multiple 
  RS-485 ports.
+ Fixed Modbus slave address end check off by 1 for HOLD, INPUT registers.
+ Fixed detecting L-STAT as EnOcean interface if commissioned online.
+ Fixed SMI rotation changes that always lead to a movement command.
+ Fixed unnecessary delays when sending or receiving MP-Bus frames.
+ Fixed Node-RED server node communication to local device.
+ Fixed non-default TX timer configuration for external NVs.
+ Don’t show warning when daisy-chained L-INX devices are supplied with AC. 
+ Fixed L-IOB native BACnet object values incorrect in some cases.
+ Fixed OnText/OffText values longer than 20 characters not displayed correctly
  in Web UI.
+ Fixed sporadic "Signal queue overflow" crash.
+ Fixed certificate check for manual software update check.
+ Security updates: OpenSSL 1.1.1n, Linux 5.10.104, OpenVPN to 2.5.6 
  (Fix for CVE 2022-0547), lighttpd 1.4.64.

LINX-102/103/112/113/120/121/150/151/153/154 7.6.0 (2022-02-09)
LINX-202/203/212/213/215/220/221             7.6.0 (2022-02-09)
---------------------------------------------------------------

+ BACnet Rev 1.16 BTL certified firmware.
+ New system register layout.
+ Allow configuring time zone and DST by using time zone name.
+ Support WiFi Enterprise key management.
+ Historic filters: Export/import filter data, allow editing filter values.
+ Added offset correction property relation to historic filters.
+ Allow to configure 3 NTP servers.
+ New clear menu on device Web UI.
+ Moved VPN setup to port configuration Web UI.
+ Added LWEB-900 VPN setup icon to device LCD UI main screen.
+ Increased maximum aggregated trend size to 200MB.
+ Allow up to 2000 trended data points in trend logs for LINX-153/154.
+ Supports extended MS/TP frames (over 501 octets).
+ Support Fault_High_Limit and Fault_Low_Limit.
+ Support Fault_Type and Fault_Parameters in Event Enrollment object.
+ Added access level select option to L-WEB user management.
+ Updated pre-installed LWEB-802 package to version 4.0.0.
+ Fixed LWEB-802 pre-installed auto-update function.
+ Fixed L-WEB user access to projects in lweb3 format.
+ Support "safe mode" in Node-RED Web UI.
+ Fixed clearing out Node-RED flows after factory reset.
+ Fixed OPC client offline transition after OPC Read timeout and external 
  host name.
+ Fixed calculation of SMI movement command and angle feedback.
+ Fixed endless loop of SMI scan if address 0 is not assigned at last.
+ Fixed L-IOB native BACnet objects to generate fault alarms.
+ Fixed potentially incorrect L-IOB Min/Max_Pres_value BACnet property values 
  after reboot.
+ SNMP MIB export corrected for data points which are not OPC exposed.
+ On-demand watch service activation for L-STUDIO.
+ Updated to node.js 12.22.3 and Node-RED 2.0.
+ Security updates: Linux 5.10.46 (LTS), chrony 4.1, dropbear 2020.81.
+ Document logout & session timeout in security log.

LINX-102/103/112/113/120/121/150/151/153/154 7.4.12 (2021-12-16)
LINX-202/203/212/213/215/220/221             7.4.12 (2021-12-16)
---------------------------------------------------------------

+ EnOcean support for D2-14-57 profile.
+ Keep L-IOB device enabled state after L-STUDIO deploy.
+ Avoid trapping older L-STAT devices in bootloader after firmware upgrade.
+ Fixed whitespaces in E-Mail subject between words with non-ASCII characters.
+ Fixed "State summary" register that could become invalid value.
+ Fixed OPC UA server MonitoredItem DataChangeFilterTrigger_StatusValue update 
  when value has not changed.
+ Fixed alarm messages if multiple alarm message properties are linked to the 
  same data point.
+ Fixed BACnet alarm messages and limits if their property relations are linked 
  to data points.
+ Fixed BACnet device ID settings by L-STUDIO being applied on every reboot.
+ Fixed access problem to local devices by LWEB-80x.
+ Fixed stalled L-STAT firmware upgrade in case the initial message is dropped.
+ Fixed crash when scanning SMI over EXT port with no LSMI-800 connected.
+ Fixed problem in L-IOB I/O test Web UI.
+ Fixed possible mismatch between L-IOB output and feedback value.
+ Fixed possible timeout during firmware upgrade over FT on many LIOB-V2 devices.
+ Fixed possible memory leak in Node-RED data point connection to remote devices.
+ Fixed OpenVPN 2.5.3 not starting due to filenames with spaces and 
  permission upgrade.
+ OpenSSL 1.1.1m security update.

LINX-102/103/112/113/120/121/150/151/153/154 7.4.10 (2021-10-01)
LINX-202/203/212/213/215/220/221             7.4.10 (2021-10-01)
---------------------------------------------------------------

+ OpenVPN client now comments out persist-tun directive in ovpn file.
+ Node-RED: Allow installation of external npm modules.
+ Setting admin password via LWEB-900 now unlocks the device Web UI login.
+ Use minimum display precision for min/max values on L-IOB Web UI.
+ Fixed missing native L-IOB BACnet updates on transitions between Manual 
  and Disabled mode. 
+ Evaluate supportedProfiles list in EnOcean templates.
+ Fixed WWAN "Connected Since" if timezone on device differs from browser.
+ Fixed WLAN verbose logging checkbox on Web UI.
+ Fixed SMI memory leak in special receive timeout cases.
+ Fixed data point value update of BACnet input objects when out-of-service.
+ Fixed backup of OPC UA server to include private key.
+ Updated pre-installed LWEB-802 package to version 3.8.4.
+ Security updates: OpenSSL 1.1.1l, deprecate RSA key exchange.
+ Upgrade to OpenVPN 2.5.3.

LINX-102/103/112/113/120/121/150/151/153/154 7.4.8 (2021-07-13)
LINX-202/203/212/213/215/220/221             7.4.8 (2021-07-13)
---------------------------------------------------------------

+ EnOcean now sends bidirectional teach-ins as unicast.
+ LTE-800: Reconfigure modem to continue supporting AT&T network after Feb 2022.
+ Improved logging when installing certificates.
+ Allow lweb users to view assigned L-WEB projects on Web UI.
+ Fixed L-IOB native BACnet objects briefly inverted after config download.
+ Fixed refresh of firmware version display after LIOB-FT firmware update.
+ Improve timeout used to detect USB disconnects of LSMI-804.
+ Fixed L-STUDIO runtime CPU stall due to excessive packet-drop logging.
+ Fixed L-STUDIO runtime receiving {POZ} packet in global zone.
+ Fixed issue that windows could shade themselves in year shade calculation.
+ Updated pre-installed LWEB-802 package to version 3.8.0.
+ Updated Node-RED to 1.3.5 and npm to 7.18.1.
+ Added the openssl command line used by Node-RED packages.

LINX-102/103/112/113/120/121/150/151/153/154 7.4.6 (2021-05-17)
LINX-202/203/212/213/215/220/221             7.4.6 (2021-05-17)
---------------------------------------------------------------

+ Fixed BACnet COV client mappings memory leak when polled.
+ Fixed wrong BACnet data point value when writing with ineffective prio.
+ Update HTTPS server when adding/deleting CA intermediate certificate.
+ Fixed OPC UA NodeID conflicts with many folders (>3000).

LINX-102/103/112/113/120/121/150/151/153/154 7.4.2 (2021-04-22)
LINX-202/203/212/213/215/220/221             7.4.2 (2021-04-22)
---------------------------------------------------------------

+ Allow assigning address 0 on M-Bus commission page.
+ Ensure E-Mail attachments up to 10MB can be transmitted.
+ Fixed 100% CPU load after Modbus TCP short network write condition.
+ Fixed SMI calibration wizard sending incorrect positions.
+ Fixed problem with initial update of L-IOB I/O status after boot.
+ Fixed usage of SMI data points directly in L-LOGICAD.
+ Fixed CG_RELOCATION issue with large IEC-61131 programs.
+ Fixed crash with IEC-61131 programs with large (> approx. 500) numbers of 
  IO variables.
+ Fixed crash in IEC-61499 protocol analyzer when loading Web page.
+ YSP: Better support for AutoCAD DXF-File exports.
+ Improve OPC client connection time when using HTTPS.
+ OPC UA server backward compatibility for checking ClientSignature and 
  device has intermediate CA certificate.
+ Security updates (Linux 5.10.11 LTS kernel, OpenSSL 1.1.1k).

LINX-102/103/112/113/153/154/202/203/212/213/215 7.4.0 (2021-02-08)
-------------------------------------------------------------------

+ Support LRS232-802.
+ Increased user register and OPC tag limit to 5000 on LINX-215.
+ Data points for L-IOB terminal name and description.
+ New L-IOB operating mode "manual disable".
+ L-IOB supports spike suppression on pulse counter inputs.
+ L-IOB Web UI now allows editing I/O description.
+ Support separate To-Normal time delay for alarms.
+ Support simple user management on the device.
+ Web UI menu structure has been reorganized.
+ Register device as VPN Client into LWEB-900 Server VPN.
+ Support AMEV-2017 AS-B extended profile.
+ Support BACnet External Notification-B (AE-N-E-B).
+ Support BACnet Minimum_On/Off_Time properties.
+ Support BACnet Min/Max_Pres_Value properties in Analog Value.
+ Support BACnet Current_Command_Priority.
+ Support BACnet LOOP PID properties/units as data points.
+ Support BACnet intrinsic reporting for LOOP object with floating limit.
+ Support BACnet Event_Message_Texts_Config.
+ Support BACnet Event_Algorithm_Inhibit, Reliability_Evaluation_Inhibit.
+ Support scheduler API in script objects.
+ Support Google IoT core.
+ 802.1X network port authentication.
+ DHCPv6 and IPv6 SLAAC.
+ Security updates: Linux kernel 5.9.8, chrony 4.0, dnsmasq 2.82.
+ Updated scripting to node.js 12.18.0.
+ L-STUDIO run-time protocol analyzer.
+ Fixed crash on HTTP request w/o HTTP_HOST header.
+ Fixed L-IOB I/O Test Web UI CSV Export button on LINX-154.

LINX-120/121/150/151/220/221 7.4.0 (2021-02-08)
-------------------------------------------------------------------

+ Data points for L-IOB terminal name and description.
+ New L-IOB operating mode "manual disable".
+ L-IOB supports spike suppression on pulse counter inputs.
+ L-IOB Web UI now allows editing I/O description.
+ Support separate To-Normal time delay for alarms.
+ Support simple user management on the device.
+ Web UI menu structure has been reorganized.
+ Register device as VPN Client into LWEB-900 Server VPN.
+ Support AMEV-2017 AS-B extended profile.
+ Support BACnet External Notification-B (AE-N-E-B).
+ Support BACnet Minimum_On/Off_Time properties.
+ Support BACnet Min/Max_Pres_Value properties in Analog Value.
+ Support BACnet Current_Command_Priority.
+ Support BACnet LOOP PID properties/units as data points.
+ Support BACnet intrinsic reporting for LOOP object with floating limit.
+ Support BACnet Event_Message_Texts_Config.
+ Support BACnet Event_Algorithm_Inhibit, Reliability_Evaluation_Inhibit.
+ 802.1X network port authentication.
+ DHCPv6 and IPv6 SLAAC.
+ Security updates: chrony 4.0, dnsmasq 2.82.
+ Fixed crash on HTTP request w/o HTTP_HOST header.

LINX-102/103/112/113/120/121/150/151/153/154 7.2.10 (2020-12-14)
LINX-202/203/212/213/215/220/221             7.2.10 (2020-12-14)
---------------------------------------------------------------

+ Fixed Modbus device probing that may not detect online devices in 7.2.8.
+ Fixed memory leak in scripts caused by connection ping.
+ Corrected shown file sizes on Documentation Web UI.
+ Fixed conversion of raw uint8 values if value spans over two Bytes.
+ OpenSSL 1.1.1i security update (CVE-2020-1971, HIGH).

LINX-102/103/112/113/120/121/150/151/153/154 7.2.8 (2020-11-04)
LINX-202/203/212/213/215/220/221             7.2.8 (2020-11-04)
---------------------------------------------------------------

+ Updated pre-installed LWEB-802 package to version 3.6.6.
+ Node-RED supports finding LOYTEC devices via SSDP.
+ Fix up persistent garbage in alarm messages for web service.
+ OpenSSL 1.1.1h security update.
+ Skip defective pollgroup configurations and resume device polling.
+ Support M-Bus meter Dornscheidt PRO380.
+ OPC UA server now creates trend nodes in Favorites folder.
+ Suppress warning if LENO-80x disconnected and no commissioned devices exist.
+ Fixed sync to RTC after manual time changes/BACnet time sync.
+ Fixed upload quota for documentation Web UI.
+ Fixed E-Mail client for devices w/o Ethernet connection.
+ L-IOB Overview Web UI fix for data point links.
+ Fixed Modbus TCP priority queue overflow in overload situations.
+ Ekey user list export has been improved.
+ MP-Bus assertion corrected when shutting down.

LINX-102/103/112/113/120/121/150/151/153/154 7.2.6 (2020-09-04)
LINX-202/203/212/213/215/220/221             7.2.6 (2020-09-04)
---------------------------------------------------------------

+ Fixed display of EnOcean repeater hops for 4BS telegrams.
+ Fixed export of default device certificate.
+ Expose I/O disable state in L-IOB data point status flags.
+ Corrected L-IOB communication between 7.2.0 and 7.2.4 devices.
+ Support redirect-gateway option in OpenVPN client.
+ Fixed unspecified behavior if > 16 L-STATs are configured on the device.
+ Fixed SMI function in case the SMI Channel device is not found.

LINX-102/103/112/113/120/121/150/151/153/154 7.2.4 (2020-08-07)
LINX-202/203/212/213/215/220/221             7.2.4 (2020-08-07)
---------------------------------------------------------------

+ Support DNS settings pushed by OpenVPN server.
+ Export device certificate also as .pem
+ Improved LSMI-804 robustness against multiple disconnects caused by EMI.
+ Fixed OPC client crash if top-level structure is polled that has invalid value.
+ Fixed NTP after a warm start due to changes in time settings.
+ Fixed sporadic XML parse error message if no Internet connectivity.
+ Fixed L-IOB config run that did not set output data points online again.

LINX-102/103/112/113/120/121/150/151/153/154 7.2.2 (2020-07-07)
LINX-202/203/212/213/215/220/221             7.2.2 (2020-07-07)
---------------------------------------------------------------

+ Support BACnet protocol rev 1.15.
+ Support re-patching Ethernet port w/o manual reboot.
+ Fix SMI sunblinds that started moving after a small delay.
+ Handle SMI power-off delay as invalid value correctly.
+ Fix file handle leak in EnOcean LENO-800 USB monitor.
+ Fixed L-IOB feedback value not being updated if output is written periodically.
+ Report error 550 in E-Mail client statistics correctly.
+ Fixed getUID node.js API.

LINX-102/103/112/113/120/121/150/151/153/154 7.2.0 (2020-06-10)
LINX-202/203/212/213/215/220/221             7.2.0 (2020-06-10)
---------------------------------------------------------------

+ Internet connection sharing.
+ SMS delivery via local LTE-800 or remote SMS gateway.
+ Support dynamic DNS.
+ Secure building automation protocols using VPN.
+ Support configuring VPN address in VPN simple server mode.
+ Support IPv6 and BACnet/IPv6.
+ Support BACnet dynamic object creation.
+ Support BACnet Event_Enrollment object.
+ BACnet verifies submitted password in RD & DCC requests.
+ Improved device backup speed.
+ Support LIOB-110 and universal analog/digital input/output (UIO).
+ Support downloading L-IOB system log.
+ Display & export I/O description on L-IOB I/O Test Web UI.
+ Fixed LIOB I/O list LCD UI over VNC connection.
+ Support remote config request from TCP/IP settings on LCD.
+ Updated pre-installed LWEB-802 package to version 3.6.2.
+ Added LWEB-802 auto-update mode.
+ Improved WLAN installation procedure.
+ Support Node-RED on the device.
+ Updated node.js version to 12.13.0.
+ Support MQTT, OCPP, Node-RED, trend CSV uploader via script package.
+ Show script resource version info on Web UI.
+ Script API dpGetProps added.
+ Security update: OpenSSL 1.1.1g and TLS 1.3.

LINX-102/103/112/113/120/121/150/151/153/154 7.0.12 (2020-04-27)
LINX-202/203/212/213/215/220/221             7.0.12 (2020-04-27)
---------------------------------------------------------------

+ Added VPN configuration to device backup.
+ Make LWEB-802 projects available when Web UI is disabled on the device.
+ Fixed occasional Modbus TCP timeout artefacts.
+ Fixed DHCP-supplied NTP servers in separate network mode.
+ Fixed OPC UA memory leak when writing structured data points.
+ Security update: prevent HTTP header injection, deprecated CBC ciphers.

LINX-102/103/112/113/120/121/150/151/153/154 7.0.10 (2020-02-14)
LINX-202/203/212/213/215/220/221             7.0.10 (2020-02-14)
---------------------------------------------------------------

+ Support LTE-800 module.
+ Show script resource version info on Web UI.
+ Security update: removed crossdomain.xml from Web server, OpenSSL 1.0.2u.
+ Fixed implicit priority of weekly schedules in Web UI.
+ MP-Bus multi-block commands fixed.
+ Fixed MP-Bus offline state if LMPBUS-804 is disconnected.
+ Modbus min/max send write request fixed for multiple RS-485 ports.

LINX-102/103/112/113/120/121/150/151/153/154 7.0.8 (2019-11-28)
LINX-202/203/212/213/215/220/221             7.0.8 (2019-11-28)
---------------------------------------------------------------

+ Make setting passwords on the Web UI mandatory.
+ BACnet client no longer writes broadcast to Restart_Notification_Recipients.
+ OpenSSL 1.0.2t security update.

LINX-102/103/112/113/120/121/150/151/153/154 7.0.6 (2019-11-18)
LINX-202/203/212/213/215/220/221             7.0.6 (2019-11-18)
---------------------------------------------------------------

+ Increased max device password length to 32.
+ HTTPS deprecated TLS versions 1.0 and 1.1.
+ Fixed large time change issue in BACnet Trend Log with Logging_Type "polled".
+ L-STUDIO: Fixed sticky NaN value in BACnet Input or LON NVs.
+ Node.js: add interface field to rule for system.firewallAllow.
+ Ensure node.js script respawn in all cases.
+ Modbus scaling corrected for integer values.
+ Improved probing L-STAT devices directly after firmware update.
+ Fixed Modbus TCP slave not reachable over VPN.
+ Fixed usage of secondary DNS server for NTP in fmw 7.0.0.
+ Fixed NTP sync to certain Windows NTP servers.
+ Corrected "in-sync" when synced to internal high-precision RTC.
+ Fixed LIOB-IP blocked by firewall after deploy.
+ Fixed L-IOB I/O status update when changing opmode on Web UI.
+ Fixed SMI sunblinds start to move after a delay.
+ Allow disabling MP-Bus device in device status "error".
+ Check type of MP-Bus device after commissioning.

LINX-102/103/112/113/120/121/150/151/153/154 7.0.4 (2019-09-04)
LINX-202/203/212/213/215/220/221             7.0.4 (2019-09-04)
---------------------------------------------------------------

+ Allow resetting L-IOB parameters on Web UI.
+ L-IOB I/O test Web UI displays and exports I/O description.
+ BACnet COV trends no longer automatically record at 0:00/12:00.
+ Fixed possible crash if Internet connection probing fails.
+ Fixed ASSERT if alarm low/high limit or deadband points to a linked favorite.
+ Fixed incorrect warning if only one LMPBUS-804 is connected to the USB port.
+ Support UTF-8 characters in certificate creation on Web UI.
+ Fixed alarm update in OPC UA server when alarm object is subscribed.
+ OPC UA server ensures session deletion with CloseSession if session has 
  not been activated.
+ Fixed memory leak in OPC UA when monitoring String or Variant data points.
+ Fixed UI in digital mode if analog threshold flag is set.

LINX-102/103/112/113/120/121/150/151/153/154 7.0.0 (2019-07-22)
LINX-202/203/212/213/215/220/221             7.0.0 (2019-07-22)
---------------------------------------------------------------

+ Support OpenVPN client and simple server.
+ Support EnOcean over L-STAT.
+ Support two LMPBUS-804 on LOYTEC devices.
+ Provide value source info on Web UI.
+ Changed COV trend periodic logging to use current timestamps.
+ Make alarm messages configurable at run-time via property links.
+ Display Internet connectivity status on Web UI status page.
+ Make protocol analyzers more verbose.
+ Support global config GUID in data point configuration.
+ Firmware upgrade enforces signature check.
+ Support custom serial protocols by scripts.
+ New scripting APIs: system, dp.writeAll, readAll with wildcards, debug filter.
+ Added web service to modify CEA-852 config server.
+ Improved MS/TP driver to keep RS-485 output enabled until entire frame is sent.
+ Ensure proper L-IOB config run after backup has been restored.
+ Improved stability when starting/stopping M-Bus, Modbus protocol analyzer 
  on command-line and Web interface.
+ L-STUDIO runtime fixed usage of strings in structures/arrays.
+ Updated OPC UA server compliance to 1.04-342.
+ OpenSSL 1.0.2s security update.

LINX-102/103/112/113/120/121/150/151/153/154 6.4.10 (2019-05-24)
LINX-202/203/212/213/215/220/221             6.4.10 (2019-05-24)
----------------------------------------------------------------

+ M-Bus support for read EEPROM and RAM.
+ M-Bus selective read incorrectly reads 0 if no data returned by meter.
+ Modbus support for write multiple COILs (function 15).
+ BACnet unsolicited COV maps accept updates independent of Notify-Type.
+ BACnet unsolicited COV support for monitoring the Status_Flag property.
+ New BACnet client map type Unsolicited COV + Poll.
+ Fixed wrong timestamps in BACnet MS/TP packet capture.
+ Fixed OPC UA server 100% CPU load if session times out before subscription.

LINX-100/101/110/111/200/201/210/211 6.4.10 (2019-05-24)
--------------------------------------------------------

+ M-Bus support for read EEPROM and RAM.
+ M-Bus selective read incorrectly read 0 if no data returned by meter.
+ Modbus support for write multiple COILs (function 15).
+ BACnet unsolicited COV maps accept updates independent of Notify-Type.
+ BACnet unsolicited COV support monitoring the Status_Flag property.
+ New BACnet client map type Unsolicited COV + Poll.

LINX-102/103/112/113/120/121/150/151/153/154 6.4.8 (2019-03-22)
LINX-202/203/212/213/215/220/221             6.4.8 (2019-03-22)
---------------------------------------------------------------

+ Support placeholders %{bacName} and %{bacDescr} for BACnet alarm messages.
+ Improved performance of live update in L-IOB Overview Web UI.
+ Fixed possible crash when activating active data point polling.
+ Fixed SMI sunblind behavior not moving/stop in automatic shading mode.
+ Fixed CSV export of KNX protocol analyzer on Web UI.
+ OpenSSL 1.0.2r security update.

LINX-100/101/110/111/200/201/210/211 6.4.8 (2019-03-22)
-------------------------------------------------------

+ Support placeholders %{bacName} and %{bacDescr} for BACnet alarm messages.
+ Improved performance of live update in L-IOB Overview Web UI.
+ Fixed possible crash when activating active data point polling.

LINX-102/103/112/113/120/121/150/151/153/154 6.4.6 (2019-02-13)
LINX-202/203/212/213/215/220/221             6.4.6 (2019-02-13)
---------------------------------------------------------------

+ Web UI menu items are highlighted on mouse-over.
+ BACnet commandable Present_Value no longer triggers an event when 
  writing with non-active priority.
+ Updated pre-installed LWEB-802 package to version 3.0.4.
+ Modbus TCP slave's number of concurrent connections increased to 32.
+ SMI driver fixed to send correct angle command instead of position command.
+ Improved CPU load if LSMI-804 is connected.
+ Fixed L-IOB parameter upload if backup of old LINX-x00/x01 has been restored.

LINX-100/101/110/111/200/201/210/211 6.4.6 (2019-02-13)
-------------------------------------------------------

+ Web UI menu items are highlighted on mouse-over.
+ BACnet commandable Present_Value no longer triggers an event when 
  writing with non-active priority.

LINX-102/103/112/113/120/121/150/151/153/154 6.4.4 (2018-12-21)
LINX-202/203/212/213/215/220/221             6.4.4 (2018-12-21)
---------------------------------------------------------------

+ Web UI/OPC server no longer round large integer values to 6 significant digits.
+ Fixed propagation of initial values in multi-slot connection.
+ Fixed IGMPv3 for multicast protocols (KNX, CEA-852.1).
+ Fixed user-installed LWEB-802 installation.
+ Fixed L-STUDIO 61131 runtime crash for var PGMs with many I/O variables.
+ Fixed relay control on LSMI-804.
+ SMI motor control corrected for target rotation > max rotation.
+ Fixed display errors if user creates a folder named "SMI".
+ OpenSSL 1.0.2q security update.
+ Fixed firmware upgrade from versions < 6.2.0.

LINX-100/101/110/111/200/201/210/211 6.4.4 (2018-12-21)
-------------------------------------------------------

+ Web UI/OPC server no longer round large integer values to 6 significant digits.
+ Fixed propagation of initial values in multi-slot connection.

LINX-102/103/112/113/120/121/150/151/153/154 6.4.2 (2018-11-13)
LINX-202/203/212/213/215/220/221             6.4.2 (2018-11-13)
---------------------------------------------------------------

+ Support more ekey models.
+ Fixed LogRead to return RemainingDuration if StartTime before first item.
+ Fixed BACnet auto client map if Protocol_Services_Supported has no COV.
+ Fixed math objects that stopped working in cascaded calculation.
+ Fixed timeToNext in generic scheduler for certain combinations of 
  scheduled events.
+ Fixed Web service download failure for partial boundary cornercase.
+ OPC client subscription on two alarm servers at the same time may lead to 
  system reboot.
+ SMI Dunkermotoren improved to stay at constant speed during movement.
+ SMI and MP-Bus data points now go offline when device is offline.
+ MP-Bus driver changed to not write default values to network.
+ MP-Bus reboot loop after parameter file download fixed.
+ Web UI: Fix Cross-Site-Scripting (XSS) and path traversal attack vectors.
+ Security update: lighttpd 1.4.49, OpenSSL 1.0.2p.

LINX-100/101/110/111/200/201/210/211 6.4.2 (2018-11-13)
-------------------------------------------------------

+ Fixed LogRead to return RemainingDuration if StartTime before first item.
+ Fixed BACnet auto client map if Protocol_Services_Supported has no COV.
+ Fixed math objects that stopped working in cascaded calculation.
+ Fixed timeToNext in generic scheduler for certain combinations of 
  scheduled events.
+ Fixed Web service download failure for partial boundary cornercase.
+ Fixed device reboot after alarm update is read by LWEB-900.

LINX-102/103/112/113/120/121/150/151/153/154 6.4.0 (2018-07-26)
LINX-202/203/212/213/215/220/221             6.4.0 (2018-07-26)
---------------------------------------------------------------

+ Safe reboot and backup before upgrade feature.
+ Automatic Web UI login after reboot.
+ Allow adding to generic trend/alarm log without losing trend data.
+ Allow using analog UIs as digital input on L-IOBs.
+ Support projects in lweb3 file format.
+ Localized Web UI.
+ Improved WLAN performance.
+ Support multiple IPs/domain names in server certificate.
+ Updated OPC UA server to latest CTT specification.
+ OPC UA server security bulletin CVE-2018-7559.
+ Support multiple M-Bus interfaces.
+ Support ekey FSX 2.1 devices and firmware upgrade.
+ Support ekey FSX UP RFID.
+ MP-Bus certified firmware.
+ Updated pre-installed LWEB-802 package to version 3.0.2.
+ Warn about settings on Web UI that are configured by L-STUDIO deploy.
+ IEC61131(L-STUDIO): Support for array types.
+ Support for script modules (BETA).
+ LINX-153/154 supports up to 10.000 user registers, 2.000 BACnet objects.
+ Disable shell login for user operator.
+ Security update: Dropbear SSH 2018.76.

LINX-100/101/110/111/200/201/210/211 6.4.0 (2018-07-26)
-------------------------------------------------------

+ Safe reboot and backup before upgrade feature.
+ Automatic Web UI login after reboot.
+ Allow adding to generic trend/alarm log without losing trend data.
+ Allow using analog UIs as digital input on L-IOBs.

LINX-102/103/112/113/120/121/150/151/153/154 6.3.5 (2018-07-12)
LINX-202/203/212/213/215/220/221             6.3.5 (2018-07-12)
---------------------------------------------------------------

+ M-Bus support for Siemens PAC2200.
+ Fixed problem causing sporadic cold reboot.
+ Improved transmission error tolerance of SMI driver.

LINX-100/101/110/111/200/201/210/211 6.3.5 (2018-07-12)
-------------------------------------------------------

+ M-Bus support for Siemens PAC2200.

LINX-102/103/112/113/120/121/150/151/153/154 6.3.4 (2018-06-21)
LINX-202/203/212/213/215/220/221             6.3.4 (2018-06-21)
---------------------------------------------------------------

+ E-Mail client tries STARTTLS first if supported by server.
+ Fixed favorites in BACnet scheduler.
+ Fixed SMI sunblind rotation becoming inaccurate after a certain amount of time.
+ Fix invalid L-LOGICAD license after firmware upgrade to 6.3.3.

LINX-100/101/110/111/200/201/210/211 6.3.4 (2018-06-21)
-------------------------------------------------------

+ Fixed missing Slot, Inactive attributed in LogInfo Web service.
+ E-Mail client tries STARTTLS first if supported by server.
+ Fixed favorites in BACnet scheduler.

LINX-102/103/112/113/120/121/150/151/153/154 6.3.3 (2018-05-07)
LINX-202/203/212/213/215/220/221             6.3.3 (2018-05-07)
---------------------------------------------------------------

+ Activate pre-installed L-LOGICAD license.
+ Fixed read from network button on Web UI.
+ Corrected LogRead with duration on COV trend multiple to return all data.
+ Fixed LogRead in reverse mode on alarm records with long descriptions.
+ OPC UA Server: Allow Anonymous connect with empty User Token.
+ EnOcean backup of SmartAck information stored in LENO.
+ MP-Bus support for Belimo VRP-M.
+ Eliminated unnecessary SMI sunblind rotation adjustments.
+ OpenSSL 1.0.2o security upgrade.

LINX-100/101/110/111/200/201/210/211 6.3.3 (2018-05-07)
-------------------------------------------------------

+ Fixed read from network button on Web UI.
+ Corrected LogRead with duration on COV trend multiple to return all data.
+ Fixed LogRead in reverse mode on alarm records with long descriptions.

LINX-102/103/112/113/120/121/150/151/153/154 6.3.2 (2018-03-08)
LINX-202/203/212/213/215/220/221             6.3.2 (2018-03-08)
---------------------------------------------------------------

+ SMI slat angle calculation improved.
+ Fixed communication issue with LSMI-804.
+ Updated pre-installed L-WEB application to 2.6.1.
+ Allow to start config run for unconfigured online L-IOBs.
+ Fixed EnOcean SmartAck teach-in under heavy air load.
+ OPC UA FindServers, GetEndpoints fixed in separate network mode.
+ Fixed problem with data points becoming overridden after reboot.
+ BACnet COV can be modified by OWS on native L-IOB objects.
+ Fixed BACnet scheduling of struct-type ASN.1 properties.
+ Fixed {%v1.name} E-mail placeholder if value is invalid.

LINX-100/101/110/111/200/201/210/211 6.3.2 (2018-03-08)
-------------------------------------------------------

+ Fixed problem with data points becoming overridden after reboot.
+ BACnet COV can be modified by OWS on native L-IOB objects.
+ Fixed BACnet scheduling of struct-type ASN.1 properties.
+ Fixed {%v1.name} E-mail placeholder if value is invalid.
+ Fixed LON scheduler expired events pruning corner-case.

LINX-102/103/112/113/120/121/150/151/153/154 6.3.1 (2018-01-26)
LINX-202/203/212/213/215/220/221             6.3.1 (2018-01-26)
---------------------------------------------------------------

+ Fixed next state in generic scheduler if events end at midnight.
+ Fixed handle leak when external NV updates complete after set offline.
+ Send EnOcean manufacturer ID during teach-in needed by Eltako devices.
+ Fixed memory leaks in EnOcean when transmitting or receiving data.
+ Correctly activate poll groups in L-STUDIO 61131 I/O driver.

LINX-100/101/110/111/200/201/210/211 6.3.1 (2018-01-26)
-------------------------------------------------------

+ Fixed regression of 6.3.0 where BACnet/IP, CEA-852 or LIOB-IP may stop working.
+ Fixed purging BACnet manual slave proxy list.
+ Fixed next state in generic scheduler if events end at midnight.
+ Fixed handle leak when external NV updates complete after set offline.

LINX-102/103/112/113/120/121/150/151/153/154 6.3.0 (2017-12-20)
LINX-202/203/212/213/215/220/221             6.3.0 (2017-12-20)
---------------------------------------------------------------

+ Improved decimal precision of floating point values in OPC server.
+ Added Web service to install certificate on device.
+ Added RNI support to LINX-153.
+ L-INX reads system settings deployed via L-STUDIO resource config.
+ KNX stack implementation improved to lower CPU load.
+ Enhanced SMI slat angle calculation for Geiger motors.
+ Improved SMI command responsiveness.
+ Fixed memory leak in EnOcean interface (since firmware 6.2.0).
+ Fixed alarm e-mail trigger for transition ACKD/ACTIVE - ACKD/INACTIVE.
+ Fixed L-IOB device data point updates broken in 6.2.4.
+ Fixed BACnet scan that did not find all devices if they have the same MAC address.
+ OpenSSL 1.0.2n security upgrade.

LINX-100/101/110/111/200/201/210/211 6.3.0 (2017-12-20)
-------------------------------------------------------

+ Improved decimal precision of floating point values in OPC server.
+ Fixed alarm e-mail trigger for transition ACKD/ACTIVE - ACKD/INACTIVE.
+ Fixed L-IOB device data point updates broken in 6.2.4.
+ Fixed BACnet scan that did not find all devices if they have the same MAC address.
+ Fixed possible deadlock between file transfer and Web UI.

LINX-102/103/112/113/120/121/150/151/153/154 6.2.4 (2017-11-23)
LINX-202/203/212/213/215/220/221             6.2.4 (2017-11-23)
---------------------------------------------------------------

+ Upgraded to kernel 4.4.94.
+ Security upgrade: OpenSSL 1.0.2l, fix KRACK vulnerability in WPA2.
+ Updated 802.11 group keys for encrypted Mesh according to standard.
+ Fixed restore of scalar L-IOB parameters by previous generation device.
+ Fixed EnOcean SmartAck teach-in "No more free mailboxes" error.
+ Fixed possible memory leak in OPC client over VPN tunnel.
+ Fixed expansion of path placeholder in to-normal alarm message.
+ Support L-STAT firmware update/backup/restore on other than first RS-485 port.
+ Fixed handling of favorites in L-STUDIO 61131 runtime.

LINX-100/101/110/111/200/201/210/211 6.2.4 (2017-11-23)
-------------------------------------------------------

+ Fixed expansion of path placeholder in to-normal alarm message.

LINX-102/103/112/113/120/121/150/151/153/154 6.2.3 (2017-09-29)
LINX-202/203/212/213/215/220/221             6.2.3 (2017-09-29)
---------------------------------------------------------------

+ Fixed decommissioning of EnOcean SmartAck devices.
+ Improved SMI positioning if a STOP is sent before a SET_STATE.
+ Fixed Web UI restore of large backup files (>12MB).
+ MP-Bus Web UI shows device path for assignment of scanned devices.

LINX-102/103/112/113/120/121/150/151/153/154 6.2.2 (2017-09-03)
LINX-202/203/212/213/215/220/221             6.2.2 (2017-09-03)
---------------------------------------------------------------

+ BACnet scan improved when reading Object_List returns unrelated error code.
+ Alarm feedback limits unit conversion fixed.
+ Allow to disable SSH access.
+ Fixed persistent values on some EnOcean data points.
+ Updated pre-installed LWEB-802 package to 2.5.0.

LINX-100/101/110/111/200/201/210/211 6.2.2 (2017-09-03)
-------------------------------------------------------

+ BACnet scan improved when reading Object_List returns unrelated error code.
+ Alarm feedback limits unit conversion fixed.

LINX-102/103/112/113/120/121/150/151/153/154 6.2.1 (2017-08-10)
LINX-202/203/212/213/215/220/221             6.2.1 (2017-08-10)
---------------------------------------------------------------

+ Telnet/FTP ports are disabled in factory defaults.
+ Fixed Modbus Slave Coil and Discrete Input in connection after status change
  (were set to '0').
+ LCD UI supports scrolling for long terminal names on I/O configuration page.
+ OPC UA server supports CreateMonitoredItems on non-data point OPC UA Nodes.
+ WLAN AP & Mesh reliability improvements.
+ Fixed SMI calibration wizard for Geiger motors.
+ Fixed memory leak in M-Bus selective read.

LINX-100/101/110/111/200/201/210/211 6.2.1 (2017-08-10)
-------------------------------------------------------

+ Telnet/FTP ports are disabled in factory defaults.
+ Fixed Modbus Slave Coil and Discrete Input in connection after status change
  (were set to '0').
+ Fixed error when loading L-IOB configuration in fmw 6.2.0.
+ Fixed memory leak in M-Bus selective read.

LINX-102/103/112/113/120/121/150/151/153/154 6.2.0 (2017-06-14)
LINX-202/203/212/213/215/220/221             6.2.0 (2017-06-14)
---------------------------------------------------------------

+ L-STUDIO 3.0 with 61131 support (BETA).
+ Support LINX-153, LINX-154, LINX-215.
+ Favorites for L-IOB native BACnet objects.
+ Show data point usage on Web UI.
+ Added data points for sun position (calculation of azimuth and elevation).
+ L-IOB parallel firmware upgrade.
+ Display IP address of devices in LIOB-IP installation Web UI.
+ Support EnOcean SmartAck devices.
+ Support LMPBUS-804.
+ MP-Bus scan including PPX mode.
+ LCD menu to upgrade firmware over USB memory stick.
+ Added 20% tolerance range for historic filter data points.
+ Automatic restore of historic filter data matching by path/name.
+ BACnet client supports unsolicited COV.
+ BACnet To-Normal no longer reported when fault alarms disabled.
+ Added dpBrowse Web service.
+ WLAN Mesh allows every Mesh Point to be a Mesh Portal.
+ Allow to disable both Ethernet interfaces when connected over WLAN.
+ Updated pre-installed LWEB-802 package to 2.4.2.
+ Security updates (Linux 4.4.55 kernel, cross-site scripting).

LINX-100/101/110/111/200/201/210/211 6.2.0 (2017-06-14)
-------------------------------------------------------

+ Favorites for L-IOB native BACnet objects.
+ Show data point usage on Web UI.
+ Added data points for sun position (calculation of azimuth and elevation).
+ L-IOB parallel firmware upgrade.
+ Display IP address of devices in LIOB-IP installation Web UI.
+ Added 20% tolerance range for historic filter data points.
+ Automatic restore of historic filter data matching by path/name.
+ BACnet client supports unsolicited COV.
+ BACnet To-Normal no longer reported when fault alarms disabled.
+ Added dpBrowse Web service.

LINX-120/121/150/151/220/221 6.1.3 (2017-04-27)
-----------------------------------------------

+ Support serial numbers w/o dash.
+ Corrected COV condition in math block connection adaptors.
+ Removed password restore option on Web UI.
+ Fixed E-Mail templates that use OPC client alarm objects.

LINX-102/103/112/113/202/203/212/213 6.1.3 (2017-04-27)
-------------------------------------------------------

+ Support serial numbers w/o dash.
+ Corrected COV condition in math block connection adaptors.
+ Removed password restore option on Web UI.
+ Fixed E-Mail templates that use OPC client alarm objects.
+ Fixed restore of LINX-112 backups on NBC-112.

LINX-100/101/110/111/200/201/210/211 6.1.3 (2017-04-27)
-------------------------------------------------------

+ Corrected COV condition in math block connection adaptors.
+ Removed password restore option on Web UI.

LINX-120/121/150/151/220/221 6.1.2 (2017-04-06)
-----------------------------------------------

+ Accept short updates from changeable NVs that advertise 31 Bytes buffer length.
+ Packet capture files included in backup.
+ Fixed Web UI to set BACnet description property data points.
+ Fixed BACnet trend client if remote Local_Date/Local_Time not available.
+ Fixed OPC UA connection duplication in statistics.
+ Fixed KNX transmission if data is never received.
+ Fixed unconfigured KNX objects to not send out group address 0.
+ SMI power-off feature can be deactivated.
+ Fixed SMI relative position offset in SET_UP/SET_DOWN commands.
+ Fixed SMI stack that could send a wrong command after a fast command sequence.
+ Improved detection and verification of attached L-WLAN adapter.
+ Security updates (lighttpd 1.4.45, OpenSSL 1.0.2k).

LINX-102/103/112/113/202/203/212/213 6.1.2 (2017-04-06)
-------------------------------------------------------

+ Accept short updates from changeable NVs that advertise 31 Bytes buffer length.
+ Packet capture files included in backup.
+ Fixed Web UI to set BACnet description property data points.
+ Fixed BACnet trend client if remote Local_Date/Local_Time not available.
+ Fixed OPC UA connection duplication in statistics.
+ Fixed KNX transmission if data is never received.
+ Fixed unconfigured KNX objects to not send out group address 0.
+ SMI power-off feature can be deactivated.
+ Fixed SMI relative position offset in SET_UP/SET_DOWN commands.
+ Fixed SMI stack that could send a wrong command after a fast command sequence.
+ Improved detection and verification of attached L-WLAN adapter.
+ Security updates (lighttpd 1.4.45, OpenSSL 1.0.2k).

LINX-100/101/110/111/200/201/210/211 6.1.2 (2017-04-06)
-------------------------------------------------------

+ Accept short updates from changeable NVs that advertise 31 Bytes buffer length.
+ Packet capture files included in backup.
+ Fixed Web UI to set BACnet description property data points.
+ Fixed BACnet trend client if remote Local_Date/Local_Time not available.

LINX-120/121/150/151/220/221 6.1.1 (2017-01-26)
-----------------------------------------------

+ Updated pre-installed LWEB-802 to version 2.4.1.
+ Auto-set IP gateway on LCD display.
+ Allow setting override value on read-only data points.
+ Fixed generic alarm conditions with default=FALSE on alarm enable DP.
+ Fixed ReturnCompleteSet option in XML-DL Web service.
+ Fixed sending e-mails to server with TLS-only login.
+ Fixed possible watchdog error when writing default values to file CP.
+ Fixed possibly blocking NVOs with min_send after the device was set 
  offline/online.
+ BACnet scheduler now ignores wildcard sec/min in scheduling algorithm.
+ Modbus TCP device polling improved for 30+ TCP slaves.
+ Modbus string registers accept entire buffer as data.
+ L-STAT devices with firmware 1.0.1 are now brought online.
+ L-KNX link detection improved.
+ OPC client's DNS resolution fixed after connection error.
+ SMI commission improved and allow changing port.
+ Security updates (kernel, dropbear, proftpd).

LINX-102/103/112/113/202/203/212/213 6.1.1 (2017-01-26)
-------------------------------------------------------

+ Updated pre-installed LWEB-802 to version 2.4.1.
+ Auto-set IP gateway on LCD display.
+ Allow setting override value on read-only data points.
+ Fixed generic alarm conditions with default=FALSE on alarm enable DP.
+ Fixed ReturnCompleteSet option in XML-DL Web service.
+ Fixed sending e-mails to server with TLS-only login.
+ Fixed possible watchdog error when writing default values to file CP.
+ Fixed possibly blocking NVOs with min_send after the device was set 
  offline/online.
+ BACnet scheduler now ignores wildcard sec/min in scheduling algorithm.
+ Modbus TCP device polling improved for 30+ TCP slaves.
+ Modbus string registers accept entire buffer as data.
+ L-STAT devices with firmware 1.0.1 are now brought online.
+ L-KNX link detection improved.
+ OPC client's DNS resolution fixed after connection error.
+ SMI commission improved and allow changing port.
+ Security updates (kernel 3.18.45, dropbear, proftpd).

LINX-100/101/110/111/200/201/210/211 6.1.1 (2017-01-26)
-------------------------------------------------------

+ Allow setting override value on read-only data points.
+ Fixed generic alarm conditions with default=FALSE on alarm enable DP.
+ Fixed ReturnCompleteSet option in XML-DL Web service.
+ Fixed sending e-mails to server with TLS-only login.
+ Fixed possible watchdog error when writing default values to file CP.
+ Fixed possibly blocking NVOs with min_send after the device was set 
  offline/online.
+ BACnet scheduler now ignores wildcard sec/min in scheduling algorithm.
+ Modbus TCP device polling improved for 30+ TCP slaves.
+ Modbus string registers accept entire buffer as data.
+ L-STAT devices with firmware 1.0.1 are now brought online.

LINX-120/121/150/151/220/221 6.1.0 (2016-11-16)
-----------------------------------------------

+ L-STAT backup/restore.
+ Chinese LCD UI (traditional and simplified).
+ EnOcean VLD support.
+ New device type system register.
+ Web UI backup/restore options to keep IP settings, passwords.
+ Support Ethernet duplex configuration.
+ Improved Modbus commissioning Web UI.
+ Optimized auto-prune of expired events in embedded calendar.
+ Added AlarmLogItemPath tag to the OPC alarm server tag collection.
+ Devices with LCD UI use DHCP in factory default.
+ SMI support for optional SET_UP/SET_DOWN commands.
+ SMI calibration wizard improvements.
+ L-STUDIO 61131 BETA version.
+ Support activation of optional L-INX features using activation PIN.

LINX-102/103/112/113/202/203/212/213 6.1.0 (2016-11-16)
-------------------------------------------------------

+ L-STAT backup/restore.
+ Chinese LCD UI (traditional and simplified).
+ EnOcean VLD support.
+ New device type system register.
+ Web UI backup/restore options to keep IP settings, passwords.
+ Support Ethernet duplex configuration.
+ Improved Modbus commissioning Web UI.
+ Optimized auto-prune of expired events in embedded calendar.
+ Added AlarmLogItemPath tag to the OPC alarm server tag collection.
+ Devices with LCD UI use DHCP in factory default.
+ SMI support for optional SET_UP/SET_DOWN commands.
+ SMI calibration wizard improvements.
+ L-STUDIO 61131 BETA version.
+ Support activation of optional L-INX features using activation PIN.

LINX-100/101/110/111/200/201/210/211 6.1.0 (2016-11-16)
-------------------------------------------------------

+ L-STAT backup/restore.
+ New device type system register.
+ Web UI backup/restore options to keep IP settings, passwords.
+ Improved Modbus commissioning Web UI.
+ Optimized auto-prune of expired events in embedded calendar.
+ Added AlarmLogItemPath tag to the OPC alarm server tag collection.

LINX-120/121/150/151/220/221 6.0.4 (2016-10-07)
-----------------------------------------------

+ E-mail timestamp placeholders use ISO date/time format.
+ Fixed trend enable data point with alarm condition.
+ Fixed %{path} place holder in alarm message for favorites.
+ Fixed feedback value of structured external value NV with persistence.
+ Fixed network status of persistent M-Bus data point connected to BACnet object.
+ Fixed background polling on external value NVs.
+ Fixed KNXnet/IP when not running on interface with default gateway.
+ Fixed parsing of EnOcean ID using correct ID offset.
+ OpenSSL 1.0.2j security upgrade.

LINX-102/103/112/113/202/203/212/213 6.0.4 (2016-10-07)
-------------------------------------------------------

+ E-mail timestamp placeholders use ISO date/time format.
+ Fixed trend enable data point with alarm condition.
+ Fixed %{path} place holder in alarm message for favorites.
+ Fixed feedback value of structured external value NV with persistence.
+ Fixed network status of persistent M-Bus data point connected to BACnet object.
+ Fixed background polling on external value NVs.
+ Fixed KNXnet/IP when not running on interface with default gateway.
+ Fixed parsing of EnOcean ID using correct ID offset.
+ OpenSSL 1.0.2j security upgrade.

LINX-100/101/110/111/200/201/210/211 6.0.4 (2016-10-07)
-------------------------------------------------------

+ E-mail timestamp placeholders use ISO date/time format.
+ Fixed trend enable data point with alarm condition.
+ Fixed %{path} place holder in alarm message for favorites.
+ Fixed feedback value of structured external value NV with persistence.
+ Fixed network status of persistent M-Bus data point connected to BACnet object.
+ Fixed background polling on external value NVs.

LINX-120/121/150/151/220/221 6.0.3 (2016-08-17)
-----------------------------------------------

+ Support LSMI-800/804.
+ WLAN Mesh graph editor floorplan and network visualization.
+ Optimized GetStatus traffic for dynamic polling of external NVs.
+ Optimize traffic of permanently used external NVs when remote node is offline.
+ Fixed value output NVs to display the correct feedback value.
+ Fixed device start-up if Favorites contain System Registers folder.
+ Fixed trend CSV with more than 127 columns.
+ Fixed missing initial evaluation of alarm enable data point in BACnet alarm 
  condition.
+ Permanently active BACnet alarms fixed when connected to M-Bus data points.
+ Fixed read-out of alarm logs with large alarm texts.
+ Fixed switch domain table/blocked domains getting cleared after reboot.
+ Automatically reconnect LENO-800 interface after EMI problem.
+ Fixed download of logiCAD RTSCode.so over Web UI.
+ Fixed Modbus TCP on Ethernet Port 2 while DHCP is waiting for IP address.

LINX-102/103/112/113/202/203/212/213 6.0.3 (2016-08-17)
-------------------------------------------------------

+ Support LSMI-800/804.
+ WLAN Mesh graph editor floorplan and network visualization.
+ Optimized GetStatus traffic for dynamic polling of external NVs.
+ Optimize traffic of permanently used external NVs when remote node is offline.
+ Fixed value output NVs to display the correct feedback value.
+ Fixed device start-up if Favorites contain System Registers folder.
+ Fixed trend CSV with more than 127 columns.
+ Fixed missing initial evaluation of alarm enable data point in BACnet alarm 
  condition.
+ Permanently active BACnet alarms fixed when connected to M-Bus data points.
+ Fixed read-out of alarm logs with large alarm texts.
+ Fixed switch domain table/blocked domains getting cleared after reboot.
+ Automatically reconnect LENO-800 interface after EMI problem.
+ Fixed download of logiCAD RTSCode.so over Web UI.
+ Fixed Modbus TCP on Ethernet Port 2 while DHCP is waiting for IP address.

LINX-100/101/110/111/200/201/210/211 6.0.3 (2016-08-17)
-------------------------------------------------------

+ Optimized GetStatus traffic for dynamic polling of external NVs.
+ Optimize traffic of permanently used external NVs when remote node is offline.
+ Fixed value output NVs to display the correct feedback value.
+ Fixed device start-up if Favorites contain System Registers folder.
+ Fixed trend CSV with more than 127 columns.
+ Fixed missing initial evaluation of alarm enable data point in BACnet alarm 
  condition.
+ Permanently active BACnet alarms fixed when connected to M-Bus data points.
+ Fixed read-out of alarm logs with large alarm texts.

LINX-120/121/150/151/220/221 6.0.2 (2016-06-17)
-----------------------------------------------

+ External NVs with poll-on-startup now don't send fetches all at once when 
  device comes online.
+ Fixed crash with KEPserverEX OPC XML-DA subscription on alarm server.
+ Fixed alarm delay when enable data point activates alarm.
+ Exclude data points with inactive alarm condition from polling.
+ OPC server alarm acknowledgment fixed, if alarm time does not specify 
  milliseconds.
+ OPC server subscription on OPC client alarm fixed.
+ Active polling memory issue with activation of group members fixed.
+ Security upgrade to OpenSSL 1.0.2h.
+ Fixed WLAN mesh MAC address filter for mpath table flooding problem.
+ Fixed MAC address after restore operation.
+ SMI memory leak on device info Web page.
+ EnOcean interface disconnect fixed after EMI problems on USB cable.
+ OPC UA TranslateBrowsePathToNodeIds issue with wrong NodeId fixed.
+ OPC UA status fixed when data point is in alarm.
+ OPC UA support for reading description of folders.

LINX-102/103/112/113/202/203/212/213 6.0.2 (2016-06-17)
-------------------------------------------------------

+ External NVs with poll-on-startup now don't send fetches all at once when 
  device comes online.
+ Fixed crash with KEPserverEX OPC XML-DA subscription on alarm server.
+ Fixed alarm delay when enable data point activates alarm.
+ Exclude data points with inactive alarm condition from polling.
+ OPC server alarm acknowledgment fixed, if alarm time does not specify 
  milliseconds.
+ OPC server subscription on OPC client alarm fixed.
+ Active polling memory issue with activation of group members fixed.
+ Security upgrade to OpenSSL 1.0.2h.
+ Fixed WLAN mesh MAC address filter for mpath table flooding problem.
+ Fixed MAC address after restore operation.
+ SMI memory leak on device info Web page.
+ EnOcean interface disconnect fixed after EMI problems on USB cable.
+ OPC UA TranslateBrowsePathToNodeIds issue with wrong NodeId fixed.
+ OPC UA status fixed when data point is in alarm.
+ OPC UA support for reading description of folders.
+ Fixed Ethernet port 2 connectivity in separate network mode.

LINX-100/101/110/111/200/201/210/211 6.0.2 (2016-06-17)
-------------------------------------------------------

+ External NVs with poll-on-startup now don't send fetches all at once when 
  device comes online.
+ Fixed crash with KEPserverEX OPC XML-DA subscription on alarm server.
+ Fixed alarm delay when enable data point activates alarm.
+ Exclude data points with inactive alarm condition from polling.
+ OPC server alarm acknowledgment fixed, if alarm time does not specify 
  milliseconds.
+ Active polling memory issue with activation of group members fixed.

LINX-120/121/150/151/220/221 6.0.1 (2016-04-13)
-----------------------------------------------

+ Fixed LIOB-Connect on LINX-22x.
+ EnOcean base ID selection for teach-in.
+ Fixed generic alarm enable if enable data point is itself alarmed.
+ Fixed time delay when disabling generic alarm.

LINX-102/103/112/113/202/203/212/213 6.0.1 (2016-04-13)
-------------------------------------------------------

+ EnOcean base ID selection for teach-in.
+ Fixed generic alarm enable if enable data point is itself alarmed.
+ Fixed time delay when disabling generic alarm.

LINX-100/101/110/111/200/201/210/211 6.0.1 (2016-04-13)
-------------------------------------------------------

+ Fixed generic alarm enable if enable data point is itself alarmed.
+ Fixed time delay when disabling generic alarm.

LINX-120/121/150/151/220/221 6.0.0 (2016-03-29)
-----------------------------------------------

+ Support SMI.
+ Added option to backup trend data.
+ Generic manual override function for data points.
+ Advanced WLAN mesh whitelist configuration.
+ Trend log in COV mode adds logging every 12 hours.
+ Support BACnet Event_Message_Texts property.
+ Feedback alarm supports alarm and feedback values in message text.
+ Alarm message size extended to 256 characters.
+ Alarm messages support %{path} placeholder.
+ Different alarm messages for low-limit and high-limit alarms.
+ Support "any COV" for analog data points.
+ E-Mail templates support placeholders for last timestamp, data point name 
  and description.
+ E-Mail templates support timestamp format specifiers.
+ OpenSSL 1.0.2g security upgrade.

LINX-102/103/112/113/202/203/212/213 6.0.0 (2016-03-29)
-------------------------------------------------------

+ Support SMI.
+ Added option to backup trend data.
+ Generic manual override function for data points.
+ Advanced WLAN mesh whitelist configuration.
+ Trend log in COV mode adds logging every 12 hours.
+ Support BACnet Event_Message_Texts property.
+ Feedback alarm supports alarm and feedback values in message text.
+ Alarm message size extended to 256 characters.
+ Alarm messages support %{path} placeholder.
+ Different alarm messages for low-limit and high-limit alarms.
+ Support "any COV" for analog data points.
+ E-Mail templates support placeholders for last timestamp, data point name 
  and description.
+ E-Mail templates support timestamp format specifiers.
+ OpenSSL 1.0.2g security upgrade.

LINX-100/101/110/111/200/201/210/211 6.0.0 (2016-03-29)
-------------------------------------------------------

+ Added option to backup trend data.
+ Generic manual override function for data points.
+ Trend log in COV mode adds logging every 12 hours.
+ Support BACnet Event_Message_Texts property.
+ Feedback alarm supports alarm and feedback values in message text.
+ Alarm message size extended to 256 characters.
+ Alarm messages support %{path} placeholder.
+ Different alarm messages for low-limit and high-limit alarms.
+ Support "any COV" for analog data points.
+ E-Mail templates support placeholders for last timestamp, data point name 
  and description.
+ E-Mail templates support timestamp format specifiers.
+ Send hostname when renewing DHCP.

LINX-120/121/150/151/220/221 5.3.2 (2015-12-18)
-----------------------------------------------

+ BACnet MS/TP supports 115200 Baud.
+ EnOcean support for profiles with 10-Bit data types.
+ Modbus TCP traffic optimization for slower devices.
+ Modbus probing compatibility with ETA devices.
+ M-Bus support for EMU professional meter.
+ Trend preview Web UI corrected for trends with > 32 trended items.
+ OPC XML-DA server data point status "overridden remote" mapped to good quality.
+ Fixed alarm summary display with double quotes in alarm messages.

LINX-102/103/112/113/202/203/212/213 5.3.2 (2015-12-18)
-------------------------------------------------------

+ BACnet MS/TP supports 115200 Baud.
+ EnOcean support for profiles with 10-Bit data types.
+ Modbus TCP traffic optimization for slower devices.
+ Modbus probing compatibility with ETA devices.
+ M-Bus support for EMU professional meter.
+ Trend preview Web UI corrected for trends with > 32 trended items.
+ OPC XML-DA server data point status "overridden remote" mapped to good quality.
+ Fixed alarm summary display with double quotes in alarm messages.
+ Fixed restore problem.

LINX-100/101/110/111/200/201/210/211 5.3.2 (2015-12-18)
-------------------------------------------------------

+ BACnet MS/TP supports 115200 Baud.
+ Modbus TCP traffic optimization for slower devices.
+ Modbus probing compatibility with ETA devices.
+ M-Bus support for EMU professional meter.
+ Trend preview Web UI corrected for trends with > 32 trended items.
+ OPC XML-DA server data point status "overridden remote" mapped to good quality.
+ Fixed alarm summary display with double quotes in alarm messages.
+ Fixed device lock-up after backup of L-IOB I/O test results.

LINX-120/121/150/151/220/221 5.3.1 (2015-11-12)
-----------------------------------------------

+ OPC UA server supports SHA2 (SHA-256).
+ OPC UA server supports multiple namespace indices.
+ OPC UA server compatibility with 1.01 clients with unsecured sessions.
+ L-STAT Modbus firmware update supported on Web UI.
+ Background polling automatic throttle on slow channels.
+ Fixed firmware upgrade from 5.0.x (or lower) to 5.3.x.

LINX-102/103/112/113/202/203/212/213 5.3.1 (2015-11-12)
-------------------------------------------------------

+ OPC UA server supports SHA2 (SHA-256).
+ OPC UA server supports multiple namespace indices.
+ OPC UA server compatibility with 1.01 clients with unsecured sessions.
+ L-STAT Modbus firmware update supported on Web UI.
+ Background polling automatic throttle on slow channels.

LINX-100/101/110/111/200/201/210/211 5.3.1 (2015-11-12)
-------------------------------------------------------

+ Background polling automatic throttle on slow channels.
+ Fixed firmware upgrade from 5.0.x (or lower) to 5.3.x.
+ Optimized file system access on low free Flash.

LINX-120/121/150/151/220/221 5.3.0 (2015-10-06)
-----------------------------------------------

+ Support OPC client data points.
+ Support custom serial protocols via the SerialComm block.
+ Web UI for project documentation.
+ Enhanced U.S. unit support.
+ Forward delay in connections.
+ Support ekey fingerprint reader devices.
+ Background polling works in parallel on different ports.
+ Polled values update value timestamp.
+ Improved trend preview Web UI.
+ Enhanced structure editor on Web UI.
+ Pre-installed LWEB-802 application on device.
+ BACnet value objects: Large analog, signed integer, integer, 
  character string, octet string.
+ BACnet Object_Name property can be made writeable.
+ BACnet Trend_Log object configuration of Notify_Type, Event_Enable and 
  Notification_Class.
+ BACnet statistics data points added.
+ Correct usage of the CP flag device-specific.
+ Support more than 255 LonMark objects for NVs on device.
+ KNX protocol analyzer on Web UI.
+ OPC UA node ID collision with structured favorites fixed.
+ OPC UA certificate extension for KEPServer version 5.16 and up.
+ Fixed sporadic CRC errors in E-Mails attachments.
+ E-Mail templates support name, description, last timestamp placeholders.

LINX-102/103/112/113/202/203/212/213 5.3.0 (2015-10-06)
-------------------------------------------------------

+ Initial version.

LINX-100/101/110/111/200/201/210/211 5.3.0 (2015-10-06)
-------------------------------------------------------

+ Web UI for project documentation.
+ Enhanced U.S. unit support.
+ Forward delay in connections.
+ Background polling works in parallel on different ports.
+ Polled values update value timestamp.
+ Improved trend preview Web UI.
+ Enhanced structure editor on Web UI.
+ BACnet value objects: Large analog, signed integer, integer, 
  character string, octet string.
+ BACnet Object_Name property can be made writeable.
+ BACnet Trend_Log object configuration of Notify_Type, Event_Enable and 
  Notification_Class.
+ BACnet statistics data points added.
+ Correct usage of the CP flag device-specific.
+ Support more than 255 LonMark objects for NVs on device.
+ E-Mail templates support name, description, last timestamp placeholders.

LINX-120/121/150/151/220/221 5.1.0 (2015-02-04)
-----------------------------------------------

+ New device info overview on the Web UI.
+ Dual-Ethernet with separate networks.
+ WLAN client and mesh support.
+ EnOcean technology added.
+ SNMP server added.
+ On-demand polling for polled data points on the L-INX.
+ Online commissioning for Modbus, M-Bus, BACnet, EnOcean.
+ Structures supported in favorites.
+ Persistent favorites with engineering units.
+ Web UI trend chart preview.
+ Generic trends support up to 1000 trended data points.
+ Scheduler preset color info in generic and BACnet.
+ Scheduler default silent mode for generic and LonMark.
+ Scheduler auto-prune of expired events.
+ E-Mail templates support format strings for display of numeric variables.
+ NVO as value data point with integrated feedback.
+ BACnet supports up to 5000 client mappings on the L-INX.
+ BACnet client support for bit-string types.
+ Modbus RTU with improved timing.
+ Modbus offline detection improved for less traffic.
+ Alarm server provides ackAll data point.
+ M-Bus string data points.
+ OPC UA supports HTTPS transport.
+ Upgrade to OpenSSL 1.0.1l.
+ Fixed persistent BACnet values when connected to CEA-709 NVs.
+ BACnet MS/TP TestResponse behavior corrected.
+ Optimized traffic in receive direction in global connections.
+ Fixed seldom trend read problem after power-cycle.

LINX-100/101/110/111/200/201/210/211 5.1.0 (2015-02-04)
-------------------------------------------------------

+ New device
