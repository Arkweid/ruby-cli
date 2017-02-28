### Test!

```
RSpec.describe Commands::Color do
  subject { described_class.new(settings:settings, ui:ui, api:api)}
  let(:settings) { double("Settings") }
  let(:ui) { double("UI") }
  let(:api) { double("Particle") }

  describe "#run" do
    it "returns early when not configured" do
      allow(ui).to receive(:with_spinner).and_yield
      expect(subject).to receive(:load_settings)
      expect(subject).to receive(:configured?).and_return(false)
      expect(subject).to receive(:not_configured)
      subject.run("blue")
    end
  end
```
