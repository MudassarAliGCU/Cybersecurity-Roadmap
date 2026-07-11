# Network Types

Every network allows devices to communicate, but not every network is built the same way. A network connecting two laptops in a bedroom is nothing like the network connecting millions of devices across an entire country. Networks are generally classified according to a few key factors:

- **Size** – how many devices are involved
- **Geographic coverage** – how much physical distance the network spans
- **Ownership** – who controls and maintains the network
- **Intended use** – what the network is designed to accomplish

Understanding these categories helps you recognize *why* a particular network is designed the way it is, instead of just memorizing labels.

---

# 📖 Why Do Different Network Types Exist?

A single network design cannot efficiently serve every situation. Think about the difference between these environments:

- **A bedroom** – just a couple of personal devices
- **A school** – dozens of computers in one building
- **A university** – multiple buildings across a campus
- **A company** – offices that may span an entire city
- **A city** – public services connecting institutions across town
- **The Internet** – billions of devices spanning the entire planet

> 📌 **Info:** Each of these environments has different needs for speed, distance, cost, and control. That's exactly why different network types were created, each one solving a different scale of problem.

---

# 🌐 Common Network Types

## PAN (Personal Area Network)

- **Definition:** A network built around a single person, usually within a few meters.
- **Coverage area:** A few meters (a room or immediate surroundings).
- **Typical speed:** Low to moderate, sufficient for personal devices.
- **Common devices:** Smartphones, smartwatches, wireless earbuds, laptops.
- **Real-world example:** Connecting your phone to wireless headphones via Bluetooth.
- **Advantages:** Simple, low power, easy to set up.
- **Limitations:** Very limited range, not designed for many devices.
- **Cybersecurity angle:** Bluetooth-based attacks often target PAN connections, since many users leave them open or discoverable by default.

---

## LAN (Local Area Network)

- **Definition:** A network confined to a single building or a small group of nearby buildings.
- **Coverage area:** A home, office, or single building.
- **Typical speed:** High, since devices are close together.
- **Common devices:** Computers, switches, printers, local servers.
- **Real-world example:** All the computers in a school computer lab connected together.
- **Advantages:** Fast, reliable, easy to secure and manage.
- **Limitations:** Limited by physical distance.
- **Cybersecurity angle:** LANs are common targets for internal attacks, lateral movement, and network scanning during penetration tests.

---

## WLAN (Wireless Local Area Network)

- **Definition:** A LAN that uses wireless signals instead of cables.
- **Coverage area:** Similar to a LAN, typically a building or home.
- **Typical speed:** High, though generally slightly slower than wired LANs.
- **Common devices:** Wireless routers, access points, laptops, smartphones.
- **Real-world example:** Connecting to Wi-Fi at home or in a coffee shop.
- **Advantages:** Convenient, no cabling required, supports mobility.
- **Limitations:** Susceptible to signal interference and wireless-specific attacks.
- **Cybersecurity angle:** WLANs introduce risks like rogue access points, weak encryption, and traffic interception, all explored later in this section.

---

## CAN (Campus Area Network)

- **Definition:** A network that connects multiple LANs across a limited geographic area, such as a university or corporate campus.
- **Coverage area:** Multiple buildings within walking distance of each other.
- **Typical speed:** High, often using fiber connections between buildings.
- **Common devices:** Core switches, routers, fiber links, campus servers.
- **Real-world example:** A university connecting its library, dormitories, and classrooms into one network.
- **Advantages:** Centralized management across multiple buildings.
- **Limitations:** Requires more infrastructure and planning than a single LAN.
- **Cybersecurity angle:** CANs require careful segmentation to prevent an issue in one building from spreading across the entire campus.

---

## MAN (Metropolitan Area Network)

- **Definition:** A network that spans a city or a large metropolitan area.
- **Coverage area:** A city or large urban region.
- **Typical speed:** Moderate to high, depending on infrastructure.
- **Common devices:** Fiber backbones, city-wide routers, ISP equipment.
- **Real-world example:** A city government connecting multiple public offices across town.
- **Advantages:** Enables communication across a wide urban area.
- **Limitations:** More costly and complex to maintain than smaller networks.
- **Cybersecurity angle:** MANs often support critical infrastructure, making them attractive targets for large-scale attacks.

---

## WAN (Wide Area Network)

- **Definition:** A network that spans a large geographic area, often across cities, countries, or continents.
- **Coverage area:** Regional, national, or global.
- **Typical speed:** Varies widely depending on the connection type.
- **Common devices:** Routers, long-distance fiber links, satellite links.
- **Real-world example:** A multinational company connecting offices in different countries.
- **Advantages:** Enables communication across vast distances.
- **Limitations:** Slower and more complex than smaller network types.
- **Cybersecurity angle:** WAN traffic often crosses public infrastructure, making encryption and secure connections essential.

---

## Other Specialized Network Types

- **SAN (Storage Area Network):** A specialized network dedicated to connecting servers to storage devices, commonly used in data centers.
- **VPN (Virtual Private Network):** A secure, encrypted connection that extends a private network across a public network, allowing safe remote communication.

---

# 🏠 Real-Life Examples

- **Home Wi-Fi** → A small WLAN connecting personal devices.
- **School Computer Lab** → A LAN connecting classroom computers.
- **University Campus** → A CAN connecting multiple buildings.
- **Bank Branch Network** → A LAN, often connected to a larger WAN linking all branches.
- **ISP Network** → Infrastructure that helps form the backbone of a MAN or WAN.
- **Mobile Network** → A wide-reaching network allowing phones to communicate almost anywhere.
- **The Internet** → The largest WAN of all, made up of countless interconnected networks.

---

# 🛡 Cybersecurity Perspective

Understanding network types matters because attacks and defenses look different depending on the network involved.

- **Penetration Testing:** Testers must understand the scope of a network, whether it's a single LAN or a company-wide WAN, before assessing its security.
- **SOC (Security Operations Center):** Analysts monitor traffic differently depending on whether they're watching a local network or traffic crossing a WAN.
- **Incident Response:** Containing a threat in a single LAN is very different from containing one that has spread across a MAN or WAN.
- **Network Administration:** Administrators must design and secure each network type according to its scale and purpose.
- **Cloud Security:** Cloud environments often behave like a virtual WAN, connecting resources across multiple physical locations.

---

# 💡 Tip

> 💡 **Memory Tip:** Think about the physical area covered.
>
> Smaller area → Smaller network type
>
> Larger area → Larger network type
>
> PAN fits in your pocket. LAN fits in a building. MAN fits in a city. WAN fits the world.

---

# ⚠ Common Beginner Mistakes

- **Thinking Wi-Fi is a network type.** Wi-Fi is a wireless technology, not a network type. A WLAN uses Wi-Fi, but Wi-Fi itself is not a classification.
- **Confusing LAN with WLAN.** A LAN can be wired or wireless. A WLAN specifically refers to a wireless LAN.
- **Assuming the Internet is the same as a WAN.** The Internet is actually made up of countless WANs, LANs, and other networks connected together, not a single WAN.
- **Believing every organization uses only one network type.** Most organizations use multiple network types simultaneously, such as a LAN inside an office connected to a WAN linking other branches.

---

# 🎯 Key Takeaways

- Networks are classified by size, coverage, ownership, and purpose.
- Different environments require different network designs.
- PAN, LAN, WLAN, CAN, MAN, and WAN represent increasing levels of geographic coverage.
- SAN and VPN serve specialized purposes beyond basic connectivity.
- Real-world environments often combine multiple network types.
- Understanding network types helps cybersecurity professionals scope their work correctly.
- Wi-Fi is a technology, not a network type.
- The Internet is a network of networks, not a single WAN.

---

# 🧠 Memory Tricks

- **PAN** → **P**ersonal, think of your **p**ocket devices.
- **LAN** → **L**ocal, think of a single building.
- **WLAN** → **W**ireless version of a LAN.
- **CAN** → **C**ampus, think of multiple buildings close together.
- **MAN** → **M**etropolitan, think of an entire city.
- **WAN** → **W**ide, think of the whole world.

```
PAN  →  Pocket
LAN  →  Building
WLAN →  Building (wireless)
CAN  →  Campus
MAN  →  City
WAN  →  World
```

---

# 🎉 Fun Fact

- The Internet is not one giant network. It is actually a massive collection of interconnected networks working together.
- Your smartphone may connect to a PAN, a WLAN, and a mobile WAN all at the same time without you noticing.
- Many large companies operate several network types simultaneously, combining LANs, WANs, and VPNs to connect their global offices.
- Some universities maintain CANs large enough to rival small city networks in scale.

---

# 📝 Quick Review

- What factors are used to classify network types?
- What is the main difference between a LAN and a WLAN?
- What does PAN stand for, and what is its typical range?
- Why is the Internet not considered a single WAN?
- Give a real-world example of a CAN.
- What role does a MAN typically serve?
- Why might a company use both a LAN and a WAN at the same time?
- What is the purpose of a VPN?
- What is the purpose of a SAN?
- Why does understanding network types matter for penetration testing?

---

# 📚 Further Reading

If any part of this lesson felt unclear, revisit **[What is Networking](What%20is%20Networking.md)** to reinforce the basic concepts before continuing.

The next lesson shifts focus from *where* networks exist to *how* they are physically and logically arranged.

---

# ➡ Next Lesson

Now that you understand *where* different network types are used, it's time to learn *how* those networks are actually designed and structured.

Continue to **[Network Topologies](Network%20Topologies.md)**.

---
