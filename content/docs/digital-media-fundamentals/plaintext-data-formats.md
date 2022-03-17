---
title: Plaintext Data Formats
draft: true
---
# Plaintext Data Formats

Files are usually something that software interfaces with, not humans. We use software to create and edit files. Yet, as we do more advanced things with software, it tends to be more the case to use file formats that are directly editable by a human hand, or are universally supported across different tools. 

Generally, we are creating data structures, and using them for _whatever_. We coudln't open up the direct data that a JPEG file gives us, it looks like gibberish, a computer parses that gibberish into an image. 

Imagine the pain of trying to edit a Powerpoint file on a computer that does not have Powerpoint installed. Developers hate that pain, and love to create a clean separation between software tools and data.

We can create a file in JSON by writing it by hand, and use it in a unity project. We could transfer the same program to a different computer, in a different operating system, and use it on a different project without having unity installed.

- XML (on top of which HTML, the markup language that websites use, is based)
- [JSON](https://www.json.org/json-en.html)
- [TOML](https://toml.io/en/)
- [YAML](https://yaml.org/)
