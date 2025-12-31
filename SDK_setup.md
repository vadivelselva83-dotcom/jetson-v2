Below is a plain .txt style file (copy-paste friendly, no formatting, no emojis, no images).

You can copy everything between the lines and save it as
JETSON_ORIN_NANO_WINDOWS_FLASH.txt

JETSON ORIN NANO 8GB – FLASHING USING WINDOWS (STEP BY STEP)

REASON FOR USING WINDOWS

NVIDIA SDK Manager works most reliably on Windows

Avoids NVIDIA website login / HTML download issues

This is a one-time step only

REQUIREMENTS

Windows 10 or Windows 11 (64-bit)

Internet on Windows PC

USB-C DATA cable (not charging-only cable)

Power adapter connected to Jetson Port 8

HDMI monitor connected to Jetson Port 7

STEP 1: DOWNLOAD SDK MANAGER ON WINDOWS

Open browser on Windows PC

Go to:
https://developer.nvidia.com/nvidia-sdk-manager

Download:
Windows x86_64 SDK Manager (.exe)

Install SDK Manager normally

Launch SDK Manager

Log in using NVIDIA account

STEP 2: PREPARE JETSON CONNECTIONS

Power OFF Jetson (unplug power cable)

Connect HDMI cable:
Jetson Port 7 → Monitor

Connect USB keyboard and mouse to Jetson

Connect USB-C DATA cable:
Jetson Port 3 → Windows PC

DO NOT power on yet

STEP 3: ENTER FORCE RECOVERY MODE

Press and HOLD the Force Recovery button on Jetson

While holding the button:
Plug power adapter into Port 8

Keep holding for 2–3 seconds

Release the Force Recovery button

Jetson is now in Recovery Mode

STEP 4: VERIFY JETSON DETECTION (WINDOWS)

SDK Manager should auto-detect Jetson Orin Nano

If not detected:

Open Windows Device Manager

You should see NVIDIA USB Device or APX

STEP 5: SELECT FLASH OPTIONS IN SDK MANAGER

In SDK Manager GUI select:

Product Category: Jetson
Hardware: Jetson Orin Nano
Target OS: JetPack 6.x (recommended)
Target Storage: NVMe

IMPORTANT:
UNCHECK ALL HOST COMPONENTS:

CUDA on host

DeepStream

Any host-side SDKs

Only Jetson OS should be selected

STEP 6: FLASH JETSON

Click FLASH

Wait 15–30 minutes

DO NOT disconnect:

Power

USB-C cable

HDMI

Jetson will reboot automatically after flashing

STEP 7: FIRST REAL BOOT

NVIDIA logo appears on monitor

Ubuntu setup wizard starts

Select language, keyboard, timezone

Create username and password

Desktop loads

UEFI shell will NOT appear again

STEP 8: VERIFY INSTALLATION

Open terminal on Jetson and run:

cat /etc/nv_tegra_release

Save the output (example: R36.2.0)

STEP 9: STOP HERE

Do NOT:

Install TensorFlow yet

Connect camera yet

Update Ubuntu packages yet

Next steps will be:

Enable performance mode

Install Docker

Enable IMX219 camera

Run TensorFlow in Docker

Build headlight detection pipeline

WHAT TO REPORT BACK

Reply with ONE of these:

SDK Manager installed on Windows

Jetson detected in recovery mode

Flashing started

Ubuntu desktop loaded
