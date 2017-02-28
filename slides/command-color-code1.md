```
module Commands
  class Color < Base
    def run(color)
      load_settings
      return not_configured unless configured?
      configure_api
      convert_color_to_hex(color)
      ui.with_spinner "Changing color" do
        send_device_color
      end
      bye(color)
    end
    # ...
```
