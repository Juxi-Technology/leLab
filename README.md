<h1 align="center">🦾 LeLab</h1>

<p align="center">
  <b>A browser interface for <a href="https://github.com/huggingface/lerobot">LeRobot</a>.</b>
</p>

<div align="center">

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Discord](https://img.shields.io/badge/Discord-Join_Us-5865F2?style=flat&logo=discord&logoColor=white)](https://discord.gg/q8Dzzpym3f)

</div>

**LeLab** is a web app that puts the full LeRobot workflow — calibrate, teleoperate, record, train, replay — into a single browser UI. Plug in your arm, open the app, and go. No CLI gymnastics, no keyboard prompts.

🤗 A web-native front door to LeRobot, designed so newcomers can get from "unboxing" to "training their first policy" in minutes.

🤗 Install and run everything with a single command.

> 📄 A copy of the upstream project. Latest official code: **<https://github.com/huggingface/leLab>**.

## Quick Start

```bash
uv tool install --with-executables-from huggingface_hub git+https://github.com/Juxi-Technology/leLab.git && lelab
```

Installs and runs LeLab + LeRobot. A browser page opens.

Step-by-step: **[Tutorials/](Tutorials/README.md)**.

## What you can do

<div align="center">
  <table>
    <tr>
      <td>🎯 <b>Calibrate</b></td>
      <td>Guided web flow for both arms — no keyboard prompts.</td>
    </tr>
    <tr>
      <td>🕹️ <b>Teleoperate</b></td>
      <td>Move the leader, the follower mirrors it. Live joint streaming.</td>
    </tr>
    <tr>
      <td>📹 <b>Record</b></td>
      <td>Capture episodes into a LeRobotDataset, with cameras.</td>
    </tr>
    <tr>
      <td>🔎 <b>Browse</b></td>
      <td>Watch the episodes of a dataset on disk — every camera, frame by frame, with a joint-motion trace. No upload required.</td>
    </tr>
    <tr>
      <td>🧠 <b>Train</b></td>
      <td>Kick off a LeRobot training job, watch logs live.</td>
    </tr>
    <tr>
      <td>🤖 <b>Run inference</b></td>
      <td>Execute a trained policy on the follower.</td>
    </tr>
    <tr>
      <td>⏪ <b>Replay</b></td>
      <td>Re-run any recorded episode.</td>
    </tr>
    <tr>
      <td>☁️ <b>Upload</b></td>
      <td>Push your dataset to the <a href="https://huggingface.co/">Hugging Face Hub</a> in one click.</td>
    </tr>
  </table>
</div>

## Camera rotation

If a camera is mounted upside down or sideways, select its **Rotation** in the camera setup on the Calibration page.
Choose 0°, 90°, 180°, or 270° clockwise. For an upside-down wrist camera, choose 180°.

LeLab saves the rotation for each camera. Setup and teleoperation previews, recorded frames, and inference use the selected rotation.
Profiles without a rotation setting use 0°.

The resolution setting describes the camera's capture resolution. A 90° or 270° rotation swaps the output dimensions.
For example, a 640 × 480 capture becomes a 480 × 640 observation. The preview shows the complete rotated frame.

Before inference, select the same rotation used for the training dataset. Check it again if you change the camera binding.
Checkpoint image dimensions do not establish image orientation. For example, 0° and 180° have the same dimensions.
The setting applies to new observations; it does not change existing recordings or checkpoints.

## Resources

- **[Tutorials](Tutorials/README.md):** step-by-step guide, from installing LeLab to running a trained policy.
- **[LeRobot](https://github.com/huggingface/lerobot):** the underlying library — go here for everything beyond the UI.
- **[Upstream LeLab](https://github.com/huggingface/leLab):** the original project. Latest official code.
- **[Discord](https://discord.gg/q8Dzzpym3f):** chat with the LeRobot community.

## Contribute

PRs welcome. Hot-reload mode for working on the code:

```bash
lelab --dev
```

Vite on `:8080`, uvicorn `--reload` on `:8000`. Installing LeLab builds the frontend bundle, so PRs never include `frontend/dist`.

<div align="center">
<sub>Originally hacked together by <a href="https://www.linkedin.com/posts/nicolas-rabault-_lerobot-hackathon-lerobot-ugcPost-7341065019368828930-jTnl/">Team LeLab at the 2025 LeRobot Worldwide Hackathon 🏆</a>, developed by the <a href="https://huggingface.co/lerobot">LeRobot</a> team at <a href="https://huggingface.co">Hugging Face</a>. This repository is a copy of <a href="https://github.com/huggingface/leLab">huggingface/leLab</a>.</sub>
</div>
