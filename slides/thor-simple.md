##  Thor in a nutshell

```
require "thor"
class MyCLI < Thor
  desc "hello NAME", "say hello to NAME"
  option :shout, type: :boolean
  def hello(name)
    output = "Hello #{name}"
    puts options[:shout] ? output.upcase : output
  end
end
MyCLI.start(ARGV)
```
