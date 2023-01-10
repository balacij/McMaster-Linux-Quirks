# Linux Tips for Students at McMaster University

At time of writing, it's 2023, and McMaster does not have much IT-related
support for Linux. As such, us Linux users are usually on our own to resolve IT
issues and navigate the proprietary software forced on us. This document
contains _some_ of the things I've encountered (everything I can remember at
least). If you have anything you can contribute, all are welcome! :)

## My Setup

### Linux Distribution

I like NixOS. You might not like it, but it's worth a try. Otherwise, Fedora is
in great shape at time of writing.

### Desktop Environment

I like and prefer to use Gnome over other desktop environments. It seems to have
the cleanest GUI and has never crashed on me. I've used it for presentations,
sound recordings, video recordings, screen sharing, etc. without issue.

## MS Teams

Unfortunately, the official MS Teams Linux application has been retired. Using
the web app version of it is okay (i.e., the PWA version), but FireFox has a few
issues with it.

## MS Word

If you want a GUI-based option, you might enjoy Google Docs or LibreOffice. WPS
Office is also another good option, but compatibility with older Word documents
was problematic for me.

However, now that I'm a graduate student, I'm enjoying LaTeX. If you want to
give LaTeX a go, look into [Overleaf](https://www.overleaf.com/) (but for
serious work, you should use your own git repo + IDE instead).

## Email (Outlook)

Unfortunately, McMaster's IT department has not allowed us to use app passwords
(at least when I got contacted them) nor is Outlook supported by major Linux web
clients (Geary, KMail, etc.), unless you want to just run it in a web browser.

Thus, I just use it in the web browser with notifications turned on.

## Wi-Fi / WLAN

The official guide says to use no validation certificate. I'm not quite sure why
they said this. Anycase, if you prefer to have a secure Wi-Fi connection, you
just need to make sure you have the commonly shared CA certificates installed on
your machine (typically installed with a `cacert` package). When registering
Mac-WiFi on your computer, I had to use the following settings:

| **Security**       	| WPA/WPA2 Enterprise               	|
|--------------------	|-----------------------------------	|
| **Authentication** 	| Protected EAP (PEAP)              	|
| **Anon. Identity** 	| (leave blank!)                    	|
| **CA Certificate** 	| (your installed cacert .crt file) 	|
| **PEAP version**   	| Automatic                         	|
| **Inner Auth.**    	| MSCHAPv2                          	|
| **Username**       	| (your Mac ID)                     	|
| **Password**       	| (your password)                   	|

With these settings, a Mac-WiFi connection works and is stable, without any real
issues.

**Note**: At time of writing, the important CA Certificate to have installed is
the current "Comodo RSA" certificates.

## VPNs / Cisco AnyConnect

NetworkManager with the OpenConnect plugin is plenty enough to avoid having to
install the AnyConnect software on your machine and use a free software
alternative that runs with tighter integration on your machine.
