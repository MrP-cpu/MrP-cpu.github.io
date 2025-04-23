---
name: Awesome Project
tools: [Tool1, Tool2]
image: image url or path here
description: Write project description here.
---

<img src="https://raw.githubusercontent.com/MrP-cpu/MrP-cpu.github.io/main/assets/images/pwnagotchi.gif" alt="Cyber GIF" width="140">

<img src="https://github.com/MrP-cpu/MrP-cpu.github.io/blob/main/assets/pwnagotchi_2.gif" alt="newCyberGif" width="140" allign=left>

# Understanding Pwnagotchi

[Pwnagotchi](https://twitter.com/pwnagotchi) is an [A2C](https://hackernoon.com/intuitive-rl-intro-to-advantage-actor-critic-a2c-4ff545978752)-based “AI” powered by [bettercap](https://www.bettercap.org/) and running on a [Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/) that learns from its surrounding WiFi environment in order to maximize the [crackable WPA key material it captures](https://pwnagotchi.ai/intro/#wifi-handshakes-101) (either through passive sniffing or by performing deauthentication and association attacks). This material is collected on disk as PCAP files containing any form of handshake supported by [hashcat](https://hashcat.net/hashcat/), including full and half WPA handshakes as well as [PMKIDs](https://www.evilsocket.net/2019/02/13/Pwning-WiFi-networks-with-bettercap-and-the-PMKID-client-less-attack/).

Inspired from : 
                [Main Website](https://pwnagotchi.ai)
                [Unofficial Website](https://pwnagotchi.org)

---

To **understand** the Pwnagotchi tool, there are two main components:

## 1. Hardware Part

This includes the physical setup required to run Pwnagotchi:

- **Raspberry Pi Zero W**: A small, power-efficient single-board computer that acts as the brain of the Pwnagotchi. It has built-in WiFi, which is essential for scanning and capturing WiFi handshakes.

<div align="center">
  <img src="https://raw.githubusercontent.com/MrP-cpu/MrP-cpu.github.io/main/assets/images/zero2W.jpg" alt="Parts diagram" style="max-width:100%; height:auto;">
  <p><em style="color: gray;">Raspberry Pi Zero W</em></p>
</div>

- **LCD Display (e.g., Waveshare 2.13 e-Ink Paper HAT+ Display)**: This is used to display real-time status updates such as the number of handshakes captured, WiFi networks in range, current mood of the Pwnagotchi (based on its reinforcement learning performance), and connectivity stats. It's a cool visual representation that makes the device look like a Tamagotchi.


<div align="center" id="carousel" style="position: relative; width: 100%; max-width: 600px; margin: auto;">
  <img src="https://raw.githubusercontent.com/MrP-cpu/MrP-cpu.github.io/main/assets/Waveshare_front.jpg" class="carousel-img" style="width: 100%; display: block;">
  <img src="https://raw.githubusercontent.com/MrP-cpu/MrP-cpu.github.io/main/assets/Waveshare_back.jpg" class="carousel-img" style="width: 100%; display: none;">
  <p><em style="color: gray;">Waveshare Display</em></p>

  <button onclick="plusSlides(-1)" style="position: absolute; top: 50%; left: 0; transform: translateY(-50%); background: rgba(0,0,0,0.5); color: white; border: none; padding: 10px;">❮</button>
  <button onclick="plusSlides(1)" style="position: absolute; top: 50%; right: 0; transform: translateY(-50%); background: rgba(0,0,0,0.5); color: white; border: none; padding: 10px;">❯</button>
</div>

<script>
  let slideIndex = 0;
  const slides = document.getElementsByClassName("carousel-img");
  showSlide(slideIndex);

  function plusSlides(n) {
    showSlide(slideIndex += n);
  }

  function showSlide(n) {
    if (n >= slides.length) slideIndex = 0;
    if (n < 0) slideIndex = slides.length - 1;
    for (let i = 0; i < slides.length; i++) {
      slides[i].style.display = "none";
    }
    slides[slideIndex].style.display = "block";
  }
</script>


So lets see the specifications of the display , we can see into the main website of the waveshare about this -> 

<div align="center">
  <img src="https://raw.githubusercontent.com/MrP-cpu/MrP-cpu.github.io/main/assets/images/specifications_waveshare.jpg" alt="Parts diagram" style="max-width:100%; height:auto;">
  <p><em style="color: gray;">Waveshare 2.13 e-Ink Paper HAT+ Display</em></p>
</div>


- **Battery Pack**: To make the setup portable and enable long-term passive sniffing, a USB power bank is typically used.


- **Optional Accessories**:
  - **MicroSD card** (for storing OS and captured data)
  - **Protective case**
  - **External WiFi adapter** (if using devices other than Pi Zero W for better performance or signal strength)

---

## 2. Software & Intelligence Part
<div align="center">
  <img src="https://raw.githubusercontent.com/MrP-cpu/MrP-cpu.github.io/main/assets/c7xh4hN.png" alt="Parts diagram" style="width: 70%; height: auto;">
  <p><em style="color: gray;">Components on the display</em></p>
</div>



This part focuses on the AI-driven functionality and software tools used:

- **Pwnagotchi OS**: A custom image based on Raspbian that runs the entire framework. It includes all the necessary tools and scripts to capture WiFi handshakes.

- **Bettercap**: The underlying packet manipulation and network monitoring tool that Pwnagotchi uses to scan for WiFi networks, sniff traffic, perform deauthentication attacks, and capture WPA handshakes or PMKIDs.

- **A2C (Advantage Actor-Critic) Reinforcement Learning**: This is the AI model that allows the Pwnagotchi to "learn" from its environment. Based on feedback (reward signals) like successful handshake captures or efficient scanning, the model adjusts its behavior to optimize future performance. This makes it smarter over time.

- **PCAP File Collection**: The captured handshakes are stored in `.pcap` format, which can later be used with offline password-cracking tools like Hashcat or Aircrack-ng to recover WiFi passwords.

- **Plugins and Community Features**: Pwnagotchi supports plugins for GPS integration, mesh networking with other Pwnagotchis, web UI access, and more.

---

Together, the **hardware** gives Pwnagotchi its body, and the **software with AI** gives it a brain and personality. It passively or actively interacts with its wireless environment to collect useful data for WiFi security research and penetration testing.
