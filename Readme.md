# HomeBox

The setup scripts for my home … thingy.

## Functions

Right now, this thing serves a disparate set of purposes. They don't really
all belong together.

* Unifi Controller for my home network
* Time Machine backups via SMB
* An SMB server. It seems kind of broken; Finder eventually forgets how
  to use resources that had been previously connected.
* An http server, with SSL, for lactobasilisk.com

## Hardware

This is an old intel NUC that I salvaged from a work project that was getting
rid of spare hardware. The CPU is unknown, and it's got 8GB of RAM.

It's running Ubuntu (currently 20.04), and its OS is installed on a 120GB
NVMe flash drive. This drive is configured for LVM, but it's just a solo
volume.

User data is stored on a 500GB OCz Vertex 3, mounted on /home.

Time machine backups are stored on a 2TB USB3 hard drive.

## Unifi Controller

The Unifi controller is run via docker. I built it around a container
I found that seems fairly popular.

## HTTP Server

A straightforward nginx server.

Letsencrypt is used to get an SSL certificate, currently via the certbot tool.
I don't love this tool because it manually fiddles with the nginx config,
and it isn't fully automatable via ansible. I'll have to figure out a better
approach.

In the future I should figure out a better approach.