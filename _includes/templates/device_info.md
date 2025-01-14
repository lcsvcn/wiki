{% assign device = site.data.devices[page.device] %}
{% include alerts/specific/note_autogenerated.html %}
{% if device.deprecated == true %}
{% include alerts/specific/warning_discontinued_device.html %}
{% endif %}
{% if device.is_unlockable == false %}
{% include alerts/specific/important_bootloader_not_unlockable.html %}
{% endif %}

## Get PixelExperience for the {{ device.vendor }} {{ device.name }}
[Get the builds here](https://download.pixelexperience.org/{{ device.codename }})

## Guides

- [Installation]({{ "devices/" | append: device.codename | append: "/install" | relative_url }})
- [Build for yourself]({{ "devices/" | append: device.codename | append: "/build" | relative_url }})
{%- if device.firmware_update %}
- [Update to a newer vendor firmware version]({{ "devices/" | append: device.codename | append: "/fw_update" | relative_url }})
{%- endif %}
- [Update to a newer build of the same PixelExperience version]({{ "devices/" | append: device.codename | append: "/update" | relative_url }})
- [Upgrade to a higher Android version (e.g. Android 10 -> Android 11)]({{ "devices/" | append: device.codename | append: "/upgrade" | relative_url }})

{% if device.note_title and device.note_title != "" %}
{% include templates/device_info_note.md %}
{% endif %}

{% if device.recovery_boot or device.download_boot %}
## Special boot modes

{% if device.recovery_boot %}
* **Recovery**: {{ device.recovery_boot }}
{% if device.vendor == "LG" %}
    {% include templates/recovery_boot_lge.md %}
{% endif %}
{% endif %}
{% if device.download_boot %}
* **Bootloader/Fastboot/Download**: {{ device.download_boot }}
{% endif %}
{% endif %}

## Find help online

You can find assistance with PixelExperience on [our Telegram group](https://t.me/pixelexperiencechat).
