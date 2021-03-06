# raspberry-pi-time-lapse

Take a time-lapse with a Raspberry Pi and Raspberry Pi Camera Module

Read the blog post on [cri.dev](https://cri.dev/posts/2020-09-01-Simple-Time-lapse-with-a-Raspberry-Pi/)

# Requirements

- Raspberry Pi + Camera Module
- imagemagick (`sudo apt-get install imagemagick`)

# Steps

1. Clone this repo on your Raspberry (`git clone https://github.com/christian-fei/raspberry-pi-time-lapse.git`)
2. Enable Camera via `raspi-config` (in "Interfacing Options")
3. Add contents of the file `crontab` to your cron schedule via `crontab -e`
4. Generate a time-lapse with e.g. `./create-time-lapse 2020-09-01`

Optionally, to speed up time-lapse creation on your PC

5. Clone this repo on your PC
6. `cp config.example.sh config.sh` and set up PI_USER and PI_HOST 
7. Sync snapshots with `./rsync-snapshots`
8. Generate a time-lapse with e.g. `./create-time-lapse 2020-09-01`


# other scripts

### `rsync` snapshots

syncs `snapshots/` with the snapshots taken on the raspberry pi

```sh
./rsync-snapshots
```

### create time-lapse of all snapshots

```sh
./create-time-lapse-all
```

pass custom FPS (default `30`)

```sh
./create-time-lapse-all 60
```
### `rsync` snapshots from the Raspberry Pi to your PC

```sh
./rsync-snapshots
```
### `rsync` time-lapses from the Raspberry Pi to your PC

```sh
./rsync-time-lapses
```

