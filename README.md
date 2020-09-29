# UserID-Magic
## Inspiration
User-ID is one of the foundational technologies that allows Palo Alto Networks firewalls to protect networks.  XSOAR was missing an integration for User-ID so we built it!  

## What it does
From XSOAR, one can retrieve or push user-id mappings to Palo Alto Networks firewalls.  There are a few use cases for this.
1 - While investigating an incident, it could be really important to pull the user mapping from the firewall to identify the user associated with the incident.  Having this automated allows the data to be pulled as soon as possible after the event is identified.
2 - In some cases, the normal sources of user to IP mappings may not provide a complete set of data.  Normally most mappings come from Active Directory.  How do you get mappings for machines that are not attached to AD like BYOD devices, guest networks, IOT or linux systems?  This integration with XSOAR provides a way.
3 - The administrator can build a lists of MAC to user mappings and IP to user mappings.  These can be used to push pre-determined user names for IPs or MAC addresses.  
4 - A syslog listen integration can be configured to receive DHCP events and automatically create User-ID mappings based on the DHCP MAC address.

## How we built it
We built a custom automation to extend the capabilities of the Panorama integration to handle User-ID functions.

## Challenges we ran into
Understanding mappings and classifiers to extract the proper fields from syslog.
Finding documentation on the APIs of various products.

## Accomplishments that we're proud of
We have a fully functional solution that gives User-ID output and supports automatic mapping of DHCP and static IP addresses.  
We built this in less than 48 hours.  

## What we learned
XSOAR product capabilities for example, mapping incoming data to fields.

## What's next for User-ID Magic
Add support for User-ID groups
Currently this has been tested with Palo Alto syslog and ISC DHCP servers.  Expand coverage to other types of DHCP servers.  
Integration to push mappings to dynamic DNS
