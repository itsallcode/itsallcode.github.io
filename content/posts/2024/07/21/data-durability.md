---
title: "Data Durability"
slug: "data-durability"
date: "2024-07-21T14:01:46+02:00"
draft: false
author: "Sebastian"
lang: "en"
---

We live in a throwaway society. Surprisingly, this also applies to important data.

There are many ways to lose data:

1. Lost data carriers
2. No backups
3. Defective backups
4. No space left on the data carrier
5. Crypto ransomware
6. File format is no longer supported

I find the last point most embarrassing. So many people have created most of their documents in proprietary data formats (e.g., Word files) and are surprised later when they can no longer read them correctly or at all with current versions of the software.

## Why Databases Are Problematic for Long-Term Storage

I vividly remember having to learn the lesson the hard way myself. When I was most actively photographing, I used [Apple Aperture](https://en.wikipedia.org/wiki/Aperture_(software)) as my photo workflow management. It was a great program to use and had great tutorials. I was smart enough to shoot and store all photos in raw format. Aperture worked lossless, that is, it stored all edits as instructions in a database. And the database is what became my downfall. When Apple announced the discontinuation of Aperture — and at that time seriously meant that people should instead use Apple Photos — it was clear to me that I had to switch to a professional and above all _durable_ solution.

However, disillusionment came with the export. I only had the choice to export either the raw files or JPGs with the changes. Losing the originals was not an option for me, so I reluctantly exported the raw files, but Aperture kept the change orders for itself.

So, I switched to Linux and [Darktable](https://www.darktable.org/). First, Darktable is open source, i.e., discontinuation does not necessarily mean that the software disappears. Second, Darktable stores everything in files. Also, the change instructions in so-called [Sidecar Files](https://docs.darktable.org/usermanual/4.0/en/overview/sidecar-files/sidecar/). That means even if Darktable ceases to exist, the change instructions and their specification are still available. Best prerequisites for a long happy data life.

For the same reason, I keep all my important information on my computer in Markdown files. I'm sure I'll still be able to read them when I'm a grandfather.

## Data Durability in Specifications

When designing [OpenFastTrace](https://github.com/itsallcode/openfasttrace), we oriented ourselves on the philosophy of Internet RFCs. The consistent use of simple text files means that the data will not eventually become noise, just because no one maintains a decoder for it anymore. OFT supports Markdown, reStructured Text, and soon AsciiDoc. All formats that can be read and edited with absolutely any text editor.

## The Cloud - 1001 Ways to Lose Data

For people who entrust their data to cloud providers, there are plenty of additional scenarios:

1. Cloud service offers no export option
2. Export mutilates the data
3. Subscription expires, and the data was not exported on time
4. No backup (yes, even cloud providers lose data)
5. Data corruption at the provider
6. Login data lost
7. Encryption passwords lost

Before pushing data to the cloud, you should always make a few things aware. Cloud providers — like most providers of proprietary services — have a very strong interest in binding customers to themselves. It's called "vendor lock-in". From a commercial perspective, this is the best thing that can happen to a provider. Once customers are sufficiently dependent, providers can raise prices significantly, let the quality deteriorate or both in combination.

By now, there is legislation in the EU that encourages providers to offer export options. Cloud operators comply with this at best reluctantly, at worst not at all. And then there is the option of malicious compliance. In this perverse variant, operators build something that, with both eyes closed, might just pass as compliant with the law, but is so cumbersome, slow, error-prone and perhaps even chargeable, that it deters customers from migrating their data.

Clouds operate under commercial constraints, including cost-saving pressure. Just because a cloud provider is large does not mean they always have all their processes under control. Anyone who doesn't believe this can search for "cloud provider incidents". But beware! The result might put you in a bad mood.

## What to do?

The key lies in not binding oneself to proprietary solutions. Some of our users have told us that they have chosen OFT because they know they will always retain control of their data and process it with other software if they no longer like OFT. This is clearly a healthy attitude, we don't take it personally, but are pleased that our users appreciate the value of migratability.

Here are my rules of thumb for durable data:

1. Use files instead of databases
2. Use simple standard formats
3. Edit and store files locally on your own machine
4. Backup to self-controlled hardware, at home or at the company
5. Additional encrypted backup in the cloud is useful as long as you choose a backup format that can be stored anywhere else at any time
6. Physical backup of the backup keys in a safe (fire-resistant)

PS: And the next person who tells me that Word is a "standard" because so many use it, I will sit on a chair and play them the definition of the word "standard" in an endless loop in all languages of the world for a day.