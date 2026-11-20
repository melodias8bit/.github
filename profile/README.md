![melodias8bit](https://raw.githubusercontent.com/melodias8bit/melodias-studio/main/docs/assets/banner.png)

# melodias8bit

Original 8-bit instrumental music and pixel-art thumbnails, generated from a vibe with local models. Every track and every frame is new material, not a conversion of the reference.

[YouTube](https://www.youtube.com/@melodias8bit)

## Projects

| Repository | What it is |
| --- | --- |
| [melodias-studio](https://github.com/melodias8bit/melodias-studio) | Rust TUI and CLI: candidate pools, review, optional judge, mastering and video assembly |

## Pipeline

1. A local LLM turns the vibe into an image prompt, and sd-server renders the thumbnail candidates at 1280x720.
2. `yt-dlp` downloads a reference track and `ffmpeg` keeps the most energetic minute.
3. ACE-Step drafts short takes, the review picks one, and ACE-Step records the full three to four minute instrument.
4. `ffmpeg` masters to -15 LUFS with fades, and the video renderer adds the still, the waveform, particles and branding.

The core runs on one GPU host against local HTTP services. The judge that preselects the pair is optional and fails open, so a run never depends on it.

## Documentation

- [Setup](https://github.com/melodias8bit/melodias-studio/blob/main/docs/setup.md)
- [Usage](https://github.com/melodias8bit/melodias-studio/blob/main/docs/usage.md)
- [Configuration](https://github.com/melodias8bit/melodias-studio/blob/main/docs/configuration.md)
- [Design RFCs](https://github.com/melodias8bit/melodias-studio/blob/main/docs/rfcs/README.md)
