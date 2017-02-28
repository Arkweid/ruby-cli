## Make commands injectable

```
class CLI < Thor
  COMMANDS = {
    color: Commands::Color,
  }
  attr_reader :commands

  desc "color COLOR", "Turn on lights this color"
  def color(name)
    commands[:color].new.run(name)
  end
end
```
