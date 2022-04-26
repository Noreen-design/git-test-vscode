# GDPS Appendix
<!-- Note to Technical writers the below is conditional text for XRC - used to be color-coded in magenta in framemaker files -->
<details>
<summary markdown="span">GDPS_CHECK_SPOF</summary>
**
The GDPS CHECK SPOF check runs on all of your GDPS systems and checks for various single points of failure in your XRC DASD configuration. The check uses the IOSSPOF interface that is provided by z/OS and documented in z/OSMVS Programming: Authorized Assembler Services Reference Volume 2 (EDT-IXG, for your z/OS release.

The checks performed are as follows:

&gt;&gt; For each XRC primary and secondary device that is found online in either an SDM or GDPS Controlling system:

-&gt; Checks whether the device has only one online path.
-&gt; Checks whether the device has all online paths through one switch.
-&gt; Checks whether all CHP IDs for the device share a single point of failure on the host I/O component for example, all CHPIDs are physically plugged into the same FICON card.
-&gt; Checks whether the device has all paths sharing a single point of failure on control unit interfaces; for example, all paths are plugged into the same HBA on a DS8000 control unit.

If any of these checks are matched, then an exception is raised.

&gt;&gt; This check runs once per day by default. This can be overridden in the HZSPRMxx member by using standard Health Checker functions.

&gt;&gt; The severity of any exception reported by this check is MEDIUM.

</details>
<!-- Note to Technical writers the below is conditional text for GM - used to be color-coded in orange in framemaker files -->
<details>
<summary markdown="span">GDPS_CHECK_SPOF</summary>
**
The GDPS_CHECK_SPOF check runs on your K-sys and checks for various single points of failure in your primary DASD configuration. The check uses the IOSS POF interface that is provided by z/O S and documented in z/OS MVS Programming: Authorized Assembler Services Reference Volume 2 (EDT-IXG), for your release of z/OS. When this check is executed in verbose mode, there will be IOSPF prefixed messages from IOS SPOF in syslog. Documentation for the IO SPF messages can be found in z/OS MVS System Messages, Vol 9 (IGF-WM), for your release of z/OS.

The checks performed are as follows:

&gt;&gt; For a each primary device in each active GM session:
-&gt; Checks whether the device has only one online path.
-&gt; Checks whether the device has all online paths through one switch.
-&gt; Checks whether all CHP IDs for the device share a single point of failure on the host I/O component; for
example, all CHPIDs are physically plugged into the same FICON card.
-&gt; Checks whether the device has all paths sharing a single point of failure on control unit interfaces; for
example, all paths are plugged into the same host adapter or host port on the control unit 11
The checks performed are as follows:
&gt;&gt; Checks that CTC connectivity is correctly defined between z/O S Proxy systems and Controlling systems. If
the check detects any missing or invalid CTC configuration definitions an SDF alert is generated and
GDPS issues message GEOH 122.11 &gt;&gt; &lt;&lt;<pp0823>&gt;&gt;Checks that the following configuration is consistent among all systems in the sysplex
(including Production and Controlling systems but not including z/OS Proxy systems), which allows the Read from Secondary function to be enabled for a device:11 -) A HyperSwap configuration is loaded and GDPS HyperSwap status is enabled. 11 -&gt; Both primary and secondary storage systems support the consistent Read from Secondary functions. 11 -&gt; READSEC must be eitherON for all systems or OFF for all systems. 1
-&gt; ZHPF enablement must be consistent on all systems. 11 &gt;&gt; &lt;&lt;<ph26663>&gt;&gt;Checks that the IOS Recovery Channel Path parameter PATH_SCOPE is correctly
defined. If PATH_SCOPE-DEVICE is detected instead of a CU definition, GDPS issues message GEOH 124E.11 Checks to see if you have defined your environment to have two Controlling systems. If the check determines that you only have one Controlling system defined, an exception will be raised. You can override this check by specifying the TWO_KSYS parameter in GEOHCPxx. This parameter has the following syntax: 11 THO_KSYS (YESMO) 1 Where the default value is YES. Specifying NO will effectively disable this part of the check. This part of the
check only runs on the Controlling systems, if not disabled. 11 &gt;&gt; Checks whether any production user catalogs are connected to the Controlling system(s) mastercatalog.
This aspect of the GDPS CHECK CONFIG check only runs on Controlling systems and generates an exception message if production catalogs are found connected to the K-sys mastercatalog.
If any of these checks are matched, then an exception is raised. 11 :&gt;) These checks run once per day by default. This can be overridden in the HZSPRMxx member by using
standard Health Checker functions. &gt;&gt; The severity of any exception reported by this check is MEDIUM.
**

</details>
<!-- Note to Technical writers the below is conditional text for GDPS GM Config - used to be color-coded in orange in Framemaker files -->
<details>
<summary markdown="span">GDPS_CHECK_CONFIG</summary>
**
Information goes here
**
</details>
