(devices-unix-block)=
# Type: `unix-block`

```{youtube} https://www.youtube.com/watch?v=C2e3LD5wLI8
:title: LXD Unix devices - YouTube
```

```{note}
The `unix-block` device type is supported for containers.
It supports hotplugging.
```

Unix block devices make the specified block device appear as a device in the instance (under `/dev`).
You can read from the device and write to it.

## Device options

`unix-block` devices have the following device options:

% Include content from [../config_options.txt](../config_options.txt)
```{include} ../config_options.txt
    :start-after: <!-- config group device-unix-block-device-conf start -->
    :end-before: <!-- config group device-unix-block-device-conf end -->
```

(devices-unix-block-hotplugging)=
## Hotplugging

Hotplugging is enabled if you set `required=false` and specify the `source` option for the device.

In this case, the device is automatically passed into the container when it appears on the host, even after the container starts.
If the device disappears from the host system, it is removed from the container as well.
