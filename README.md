# jetson-v2
SD Card Image setup

JETSON ORIN NANO 8GB – FIRST BOOT & SETUP STEPS (COPYABLE)

UNBOX & PREPARE

Take out the Jetson Orin Nano Developer Kit

Place it on a non-conductive surface

Do NOT power it yet

INSTALL NVMe SSD (IMPORTANT – BEFORE POWER)

Flip the board upside down

Insert M.2 NVMe SSD (2280) at an angle

Push it down gently

Secure with the screw

Flip board back upright

IDENTIFY IMPORTANT PORTS (FROM YOUR IMAGE)

Port 7 = HDMI (video output)

Port 8 = DC barrel jack (power input)

USB ports = keyboard/mouse

Ethernet port = optional internet

CONNECT CABLES (ORDER MATTERS)

HDMI cable → Port 7 → Monitor

USB keyboard → any USB port

USB mouse → any USB port

Ethernet cable → router (optional but recommended)

Power adapter → Port 8 (CONNECT LAST)

POWER ON

As soon as power is connected, the board turns ON automatically

No power button exists

FIRST BOOT SETUP (ON MONITOR)

NVIDIA logo appears

Ubuntu / JetPack setup wizard starts

Select language, keyboard, timezone

Create username and password

WHEN ASKED FOR STORAGE:
→ SELECT NVMe SSD (NOT removable storage)

WAIT FOR DESKTOP

Initial boot may take 5–10 minutes

You should reach Ubuntu desktop

OPEN TERMINAL & VERIFY SYSTEM
Run these commands:

uname -a
lsblk
df -h

Confirm NVMe is mounted and has free space

CHECK JETPACK / L4T VERSION (VERY IMPORTANT)
Run:

cat /etc/nv_tegra_release

Save the output (example: R36.2.0)

This determines which Docker images you will use later

SET PERFORMANCE MODE (RECOMMENDED)
Run:

sudo nvpmodel -m 0
sudo jetson_clocks

INSTALL DOCKER (ONE-TIME, WHILE ONLINE)
Run:

sudo apt update
sudo apt install -y docker.io
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker $USER

Log out and log back in

Verify Docker:

docker run hello-world

STOP HERE

DO NOT connect the camera yet

DO NOT install TensorFlow manually

DO NOT update Ubuntu beyond JetPack

NEXT STEPS (AFTER THIS FILE)

Enable IMX219 camera via Jetson-IO

Pull correct NVIDIA L4T Docker image

Run TensorFlow inference in Docker

Build headlight detection pipeline

WHEN YOU ARE READY
Paste the output of this command:

cat /etc/nv_tegra_release

and we will continue step-by-step with:

exact Docker image

camera enablement

TensorFlow setup

offline-ready deployment
