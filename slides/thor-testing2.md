## Testing argument parsing

```
RSpec.describe CLI do
  describe "color" do
    let(:command) { instance_double("Commands::Color") }
    it "returns an error with a missing argument" do
      args = ["color"]
      expect { run_command :configure, command, args }.
        to raise_error Thor::InvocationError
    end
    it "passes the color to the Color command" do
      args = ["color", "green"]
      expect(command).to receive(:run).with("green")
      run_command :color, command, args
    end
  end
end
```
