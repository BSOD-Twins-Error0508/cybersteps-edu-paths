Welcome! Before our next session, we'll explore the physical components that make up a computer system. Understanding the hardware – the tangible parts of a computer – is fundamental to understanding how computers work, regardless of the specific type you use.

## What is Hardware?

Computer hardware refers to the physical parts of a computer system – the components you can actually touch. This includes everything inside the computer's case or enclosure (like the main chips and memory) and the peripherals you connect to it (like keyboards and monitors). Software, on the other hand, consists of the programs and instructions (like the operating system and applications) that tell the hardware what to do. Hardware and software work together to make a computer functional.

## Core Components Inside a Computer

Most computers, from desktops to laptops like MacBooks, are built around these core parts, though their specific form factor and integration may vary:

1. **Motherboard (or Mainboard / Logic Board)**:
    
    ![image.png](attachment:2d21c51c-1325-405b-91e9-1eb81eb36ea7:image.png)
    

- Think of this as the central nervous system and skeleton of the computer. It's a large printed circuit board (PCB) that connects almost all other components.
- It contains sockets or connections for the CPU, slots or connections for RAM, connectors for storage devices, expansion slots (more common in desktops), and ports for external peripherals.
- All components communicate with each other through the pathways (called buses) on this board. In Macs, this is often called the Logic Board, and components may be permanently attached (soldered).

1. **Central Processing Unit (CPU)**:

![image.png](attachment:caceb704-be3d-49c8-9567-6dc4f2872018:image.png)

- Often called the "brain" of the computer. The CPU executes instructions from software. It performs calculations, makes logical comparisons, and moves data around.
- CPU speed is measured in Gigahertz (GHz). A higher GHz generally means the CPU can perform more operations per second.
- Modern CPUs often have multiple "cores" (e.g., dual-core, quad-core, octa-core). Each core can process instructions independently, allowing the computer to handle multiple tasks more efficiently (multitasking).

1. **Random Access Memory (RAM)**:

![image.png](attachment:e5fc5215-86be-41c8-b35a-d5f03d971438:image.png)

- RAM is the computer's short-term memory. It's where the operating system, applications, and data currently in use are kept so they can be quickly reached by the CPU.
- RAM is "volatile," meaning its contents are lost when the computer is turned off.
- Memory capacity is measured in Gigabytes (GB). More RAM generally allows you to run more applications simultaneously and handle larger datasets without slowdowns.
- In many PCs, RAM comes in modules (sticks). In some modern laptops and integrated systems (like Apple Silicon Macs), memory might be soldered directly to the main board or integrated into the CPU package (like "Unified Memory") and cannot be upgraded after purchase.

1. **Storage Devices**:

![image.png](attachment:8f5cb47b-9083-4242-99c0-1bd3de1f2ab0:image.png)

- These are the components used for long-term data storage. Unlike RAM, they are "non-volatile," meaning data persists even when the power is off.
- **Hard Disk Drive (HDD)**: Traditional storage using spinning magnetic platters. Found in older or budget computers, offering large capacity at low cost but are slower and less durable than SSDs.
- **Solid State Drive (SSD)**: Use flash memory chips. SSDs are significantly faster, quieter, more durable, and consume less power than HDDs. Virtually all modern computers, especially laptops, use SSDs. In some laptops (like many MacBooks), these may be soldered and not upgradable.
- Storage capacity is measured in Gigabytes (GB) or Terabytes (TB). 1 TB = 1000 GB.

1. **Graphics Processing Unit (GPU)**:

![image.png](attachment:9c65e98f-da13-49f6-b3fc-0757f24a53f6:image.png)

- The GPU is specialized hardware for handling graphics and image processing. It takes the load off the CPU for tasks like rendering images, videos, animations, and the user interface.
- GPUs can be **integrated** (part of the CPU or motherboard chipset, suitable for everyday tasks) or **dedicated** (a separate, more powerful chip or card, better for gaming, video editing, etc.).

1. **Power Supply Unit (PSU) / Battery & Adapter**:
    - Desktop computers use an internal PSU to convert AC wall power to the DC voltages needed by components.
    - Laptops have an internal **battery** for portability and use an external **power adapter** (the "brick") to charge the battery and run off AC power.
2. **Cooling Systems**:
    - Components like the CPU and GPU generate significant heat. Cooling systems (fans, heat sinks, heat pipes, liquid cooling, or passive dissipation through the chassis) are essential to prevent overheating, which can cause performance issues or damage.

## Think about it

Given that crucial components in some modern laptops (like Unified Memory and SSDs in MacBooks) are soldered to the main board and cannot be upgraded, how does this influence your decision-making process when selecting the specifications (Memory, Storage) for a new computer?

## Connecting Everything: Ports and Peripherals

Hardware also includes the devices you connect _to_ the computer:

- **Input Devices**: Allow you to send information _to_ the computer (e.g., Keyboard, Mouse, Trackpad, Microphone, Webcam).
- **Output Devices**: Allow the computer to send information _to_ you (e.g., Monitor/Display, Printer, Speakers/Headphones).
- **Ports**: These are the physical sockets used to connect peripherals. Common types include:

![image.png](attachment:a3daf873-94c5-459a-928d-935b89724b2b:image.png)

- **USB-A**: The traditional rectangular USB port, used for many peripherals like mice, keyboards, printers, and older external drives. Different versions exist (2.0, 3.0, etc.) offering different speeds.
- **USB-C**: A smaller, oval, reversible connector. Used for data transfer, display output, and power delivery. Increasingly common on modern devices.
- **Thunderbolt (often using USB-C connector)**: A high-speed interface developed by Intel and Apple, commonly found on Macs and some PCs. Uses the USB-C connector type but offers much faster data transfer speeds (up to 40Gb/s), supports multiple high-resolution displays, and power delivery. Ideal for demanding peripherals like fast external SSDs, docking stations, and high-end monitors.
- **HDMI**: Standard port primarily used for connecting monitors and TVs.
- **DisplayPort**: Another common standard for connecting monitors, often preferred for higher resolutions and refresh rates.
- **Ethernet (RJ-45)**: Used for wired network connections. Common on desktops and docking stations, less common directly on thin laptops.
- **Audio Jack**: Standard 3.5mm port for headphones, speakers, and microphones.
- **SD Card Slot**: Allows reading memory cards from cameras, available on some laptops and desktops.
- **MagSafe**: A magnetic charging connector used on some Apple MacBook models, designed to detach easily if the cord is pulled.

## Try it yourself

1. Look at the sides of your MacBook. Identify the types of ports available. Which ones do you use most often? Do you need adapters or a hub/docking station for any of your peripherals (like older USB devices, Ethernet, or multiple monitors)?
2. Open "System Information" on your Mac (Applications > Utilities > System Information, or hold the Option key and click the Apple menu  > System Information...). Explore the "Hardware" section. Can you find information about your Chip (Processor), Memory, Graphics, and Storage? Compare what you see to the configurations described above. (Don't worry if some details seem complex, just get a feel for what information is available).

This overview covers the basics of computer hardware. In our live session, we'll discuss these components in more detail and look closer at how to identify them using macOS tools.