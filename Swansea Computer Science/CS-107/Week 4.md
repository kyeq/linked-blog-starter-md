![[Screenshot 2026-10-19 at 15.19.48.png]]#CS107 

### Tech Jargon

#### Processor
The processing unit (usually a CPU) executes instructions and carries out low-level operations.

Key details and rules of thumb:
- number of cores: how many things it can do in parallel, more is better.
- Speed: how fast it can process instructions, faster is better.

#### RAM
RAM: Primary memory, allows you to have more data / larger programs in use at the same time. RAM is the main memory in the diagram: the store the bus reaches on every fetch and every data read. 

Key details and rules of thumb:
- size: how much information it can fit in memory, more is better.
- speed: how fast can information be read/written, higher is better.

#### Types of memory
- **Random Access Memory (RAM)**: Each location can be accessed and changed.
- **Read Only Memory (ROM)**: Each location can be accessed, but not chaned/modified.

RAM is volatile, it stores the values with electrical voltage and when this voltage is removed the information is lost. ROM is not volatile, the values are 'hard coded' into the address. 

**Main Memory:** Storage location which can be directly accessed by the CPU, usually physically located on the computer to allow for extremely fast access to active program and data information.

**Secondary Memory:** Storage locations which are used for non-active information stored over longer periods of time. This can include devices such as magnetic disks, optical disks, and solid state drives.

#### Magnetic Disk Storage

![[Screenshot 2026-10-19 at 15.17.27.png]]

#### Magnetic Disk Layout
- **Track:** A physical, circular path on the disk surface. This is where the data is written/read.
- **Sector:** A sub-division of a track, storing a fixed amount of data.
- **Block:** Chunk of data on disk, identified by both track and sector. The minimal storage unit of a disk.

![[Screenshot 2026-10-19 at 15.19.48 1.png]]

**Cylinder:** A set of concentric tracks on all disks in a drive.
**Spindle**: The central shaft that holds the disks and spins them all together at a constant speed.
**Read/write head:** The sensor that flies just above a surface and magnetises it to write, or detects its magnetism to read. One head per surface.
**Arm:** The assembly that carries the heads in and out.

![[Screenshot 2026-10-19 at 15.21.29.png]]

#### Magnetic Disk Access

**Seek time**: Time for read/write head to move over correct track.
**Latency:** Time for sector to be rotated under read/write head.
**Access Time:** time for block to start being read (seek + latency)
**Transfer Rate**: rate at which data moves from disk to memory.

#### Optical Disks

**Compact disk (CD):** A disk that uses a laser to read information stored optically on a plastic-coated disk; data is evenly distributed around spiral track.
**Digital versatile disk (DVD):** Used for storing audio and video.
**Blu-ray:** Higher capacity DVD (using a blue light laser) allowing higher resolution video, etc.

#### Solid State Drives

- Uses integrated circuits to store data, rather than the magnetic or optical elements seen previously.
- Typically uses flash memory to store the information. This stores the value even when the power is removed, great for secondary storage.
- As it uses logical gates (transistors) to store data, there are no moving parts. This makes them much faster and quieter than mechanical disk drives, and provides impact resistance.

### Parallel Computing
We discussed the Fetch-Decode-Execute cycle, and the limitations of the Von Neumann bottleneck. In some scenarios, it is beneficial to perform some operations **concurrently (at the same time)**

This is called **parallelism**, and there are four common approaches to this task, depending on the application.

Approaches to parallelism:
- Bit-level
- Instruction-level
- Data-level
- Task-level

Modern computers often have multiple **cores** or processing units. 
Each processor is then able to carry out its own instructions.

**Bit-level parallelism**
Individual bits can be processed simultaneously.

For example...
- If our computer's word size is 8 bits, it would require 2 operations to process a 16-bit value.
- With a 16-bit word size we could do this task in a single operation.

To add 16-bit numbers would require two applications of this adder, but we had a 16-bit adder then we only need to apply it once.

**What is "word size"?**
Word size: The number of bits the processor handles as one unit - the width of its registers, ALU and data bus. Individual bits can be processed simultaneously. 

**Why is matters:** Word size sets how much data each instruction moves, the largest value the CPU handles natively, and how much memory is can address.

#### Instruction-level parallelism
Some instructions can be executed independently.
This can take two main forms:
- Pipelining is the concept of overlapping instructions which can be carried out in series. For example, in the Fetch-Decode example, we can start fetching the next instruction while our current one is decoding.
- Superscalar is the concept of having multiple execution units which allow us to execute multiple instructions per cycle, increasing the bandwidth of our processor.

#### Data-level parallelism
Application of single instruction to many pieces of data simultaneously. Single Instruction, Multiple Data (SIMD)

#### Task-level parallelism
Entire tasks an be completed simultaneously, either with the same data or on different data.
Multiple instructions, multiple data (MIMD)