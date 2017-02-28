```
require "tty-prompt"
require "tty-spinner"
class UI
  def ask(question, options = {})
    if options[:password]
      prompt.mask(question)
    else
      prompt.ask(question, options)
    end
  end
  def with_spinner(message = "", &block)
    s = TTY::Spinner.new ":spinner #{message}"
    s.run(&block)
  end
end
```
