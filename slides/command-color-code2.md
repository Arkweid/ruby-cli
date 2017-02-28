```
module Commands
  class Color < Base
    # ...
    def send_device_color
      device = api.device(device_name)
      device.function("color", color_hex)
    end
  end
end
```
