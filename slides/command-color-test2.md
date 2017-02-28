## Test more!
```
describe "#send_device_color" do
  it "calls the color device function" do
    subject.device_name = "dev"
    subject.color_hex = "#0000ff"
    device = double
    expect(api).to receive(:device).with("dev").and_return(device)
    expect(device).to receive(:function).with("color", "#0000ff")

    subject.send_device_color
  end
end
```
