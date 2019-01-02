# CyberSource Flex Samples

This repository provides simple examples demonstrating usage of the CyberSource Flex SDK using either a headless javascript call (jsp-flexjs) or a fully customizable hosted field/microform which is incorporated into your checkout page.  For more details on Secure Acceptance Flex visit our Developer Guide at https://developer.cybersource.com/api/developer-guides/dita-flex/SAFlexibleToken.html

## Usage

1. Clone or download this repository.
2. Update webapp/WEB-INF/credentials.properties with your CAS/Sandbox credentials
3. Run mvn package in the sample you want to try (jsp-microform or jsp-flexjs)
4. Copy the output WAR file to your web server directory

## Requirements
* Java 1.8 or later . 
* Tomcat web server .  

**_NOTE: While this sample currently requires Java we are planning to release samples in other languages/stacks over the coming months_**

## API Reference
While these examples use the Javascript libraries which we recommend as the most convenient option you can try out the APIs behind the Javascript SDKs by visiting out API Reference at https://developer.cybersource.com/api/reference/api-reference.html

## Background on PCI-DSS

Storing your customer’s card data can dramatically increase your repeat-custom conversion rate, but can also add additional risk and [PCI DSS](https://www.pcisecuritystandards.org/pci_security/) overhead. You can mitigate these costs by tokenizing card data. CyberSource will store your customer’s card data within secure Visa data centers, replacing it with a token that only you can use. 

Secure Acceptance Flexible Token is a secure method for Tokenizing card data, that leaves you in total control of the customer experience. Your customer’s card number is encrypted on their own device, for example inside a browser or native app, and sent directly to CyberSource. This means card data bypasses your systems altogether. This can help you qualify for [SAQ A](https://www.pcisecuritystandards.org/documents/Understanding_SAQs_PCI_DSS_v3.pdf) based PCI DSS assessments for web based integrations, and [SAQ A-EP](https://www.pcisecuritystandards.org/documents/Understanding_SAQs_PCI_DSS_v3.pdf) for native app integrations.

You are in total control of the look and feel, with the ability to seamlessly blend the solution in to your existing checkout flow, on web or in-app.

On-device encryption helps to protect your customers from attacks on network middleware such as app accelerators, DLPs, CDNs, and malicious hotspots.

The token can be used in lieu of actual card data in server-side requests for other CyberSource services, for example to make a payment, using our REST APIs : https://developer.cybersource.com/api/reference/api-reference.html

## Samples

### Javascript Sample

This sample demonstrates how your checkout form can remain exactly as it is today, the only addition will be a javascript call to tokenize the customers credit card information directly FROM their browser (to CyberSource) replacing that data with a secure PCI-compliant token which you can then post up to your server along with the other non-PCI order data.  This provides PCI-DSS SAQ-A(EP) level compliance for your application.

### Microform Sample

This sample demonstrates how you can replace the sensitive data fields (credit card number) on your checkout form, with a field (Flex Microform) hosted entirely on CyberSource servers.  This field will accept and tokenize the customers credit card information directly FROM their browser (to CyberSource), replacing that data with a secure PCI-compliant token which you can then post up to your server along with the other non-PCI order data.  This provides PCI-DSS SAQ-A level compliance for your application as even your client-side code does not contain any code to handle the credit card number.
