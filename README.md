- build spotifyd from source
```
sudo apt install rustc cargo libasound2-dev libssl-dev pkg-config
cargo build --release
```
- make spotifyd command available to the system:
```
sudo ln -s target/release/spotifyd /usr/bin/spotifyd
```
- edit spotifyd.conf and make sure everything is correct
- edit contrib/spotifyd.service. make sure all paths are correct
- create systemd service
```
mkdir ~/.config/systemd
mkdir ~/.config/systemd/user
sudo cp contrib/spotifyd.service ~/.config/systemd/user/
```

- enable service
```
systemctl --user enable spotifyd.service
systemctl --user start spotifyd.service
```
