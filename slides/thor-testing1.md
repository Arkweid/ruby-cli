## Make commands injectable

```
class CLI < Thor
  COMMANDS = {
    configure: Commands::Configure,
    color: Commands::Color,
  }
  attr_reader :commands # set to COMMANDS in initialize

  desc "color COLOR", "Turn on lights this color"
  def color(name)
    commands[:color].new.run(name)
  end
end
```
