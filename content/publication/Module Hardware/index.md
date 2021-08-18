---
title: "Module Hardware"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin

# Author notes (optional)
author_notes: ""

date: "2021-08-11"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: ""

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["0"]

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: ""

abstract: ""

# Summary. An optional shortened abstract.
summary: Beside the the school we have to complete different modules in our company. The first topic is about Hardware.

tags: [PiBS]

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**Unsplash: Martin Katler**](https://unsplash.com/photos/7wCxlBfGMdk)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
{{% callout note %}}
  1. <b> In the following part i would like to present you the different components, which are inside of a PC, server or a notebook.</b>
{{% /callout %}}

<b>Computer case:</b> Inside of the computer case you will find all following components of a Computer. The main idea is to protect the interior. It also contributes to a visual aspect of the computer.

![Computer Case](computer-case.jpg "<b>Computer case</b> (Unsplash: Onur Binay)")

<b>CPU (central processing unit):</b> The CPU is the brain of the computer. It does the logical calculations, processes data and passes informations to the other parts.

![CPU](processor.jpg "<b>CPU</b> (Unsplash: Fidel Fernando)")

<b>Motherboard:</b> The motherboard or also known as mainboard connects all parts to each other and enables communication between each other components.

![Motherboard](motherboard.jpg "<b>motherboard</b> (Unsplash: Thomas Jensen)")

<b>RAM (random access memory):</b> It's a temporary storage space to process data fast. The RAM is located nearby the CPU, to keep the latency as low as possible.

![RAM](ram.jpg "<b>RAM</b> (Unsplash: Luan Gjokaj)")

<b>Storage device:</b> A distinction is made between the HDD (hard disk drives) and the SSD (solid state drives). The HDD is working mechanical like a music turntable, while the SSD is a flash storage device. Both of them store data persistently.

![HDD](hdd.jpg "<b>HDD</b> (Unsplash: Art Wall - Kittenprint)")

<b>PSU (power supply unit):</b> The electricity from the power socket goes truth the PSU and is distributed to the various components.

![PSU](psu.jpg "<b>PSU</b> (Unsplash: Luke Hodde)")

<b>GPU (graphics processing unit):</b> It's a specialized chip to calcultate all graphic outputs fast. A CPU can theoretically do the same, but it takes much longer than the GPU.

![GPU](gpu.jpg "<b>GPU</b> (Unsplash: Nana Dua)")

<b>Cooling unit:</b> All components that consume electricity, are generating heat. Because of this reason, you need a cooling unit to prevent damages on the different modules.

![Cooling unit](cooling-unit.jpg "<b>Cooling unit</b> (Unsplash: Barez Omer)")

{{% callout note %}}
  2. <b>Advanced questions about my notebook (ThinkPad X1):</b>
{{% /callout %}}

{{< hl >}}How fast (in GHz) is the CPU you are using right now?{{< /hl >}}<br>
➡️Intel(R) Core(TM) i7-10510U CPU @ 1.80GHz - 2.30 GHz
<p></p>
{{< hl >}}What chipset is on the motherboard? Could there be more options?{{< /hl >}}<br>
➡️On my motherboard is a SoC (System-on-a-Chip)<br>
➡️ Southbridge / Northbridge / System-on-a-Chip
<p></p>
{{< hl >}}How many gigabytes of RAM are in the PC you’re using?{{< /hl >}}<br>
➡️16.0 GB (15.8 GB usable)
<p></p>
{{< hl >}}What is/are the storage medium/media in your PC?{{< /hl >}}<br>
➡️500GB SSD
<p></p>
{{< hl >}}Where is the PSU in your PC? What about a laptop?{{< /hl >}}<br>
➡️Inside the PC<br>
➡️External Adapter
<p></p>
{{< hl >}}Do you have a GPU?{{< /hl >}}<br>
➡️iGPU in the CPU; Intel HD Graphics 620 (GT2)
<p></p>
{{< hl >}}How does the cooling work in your device? What about a smartphone?{{< /hl >}}<br>
➡️My notebook is cooled from below by two fans<br>
➡️Smartphones in general; Heatpipe, which transmits the heat to the outside<br>
<p></p>
{{% callout note %}}
  3. <b> This are the parts that i would buy, if i would build my own PC. Link ➔</b>
  [Digitec](https://www.digitec.ch/de/shopList/show/ABB019BA20D90765AFCEC16A2800DF8C)
{{% /callout %}}
{{% callout note %}}
  4. <b>Task – Bits and bytes</b>
{{% /callout %}}
{{< hl >}}Say you have a gigabit internet connection (downstream). How many kilobytes can you download per second?{{< /hl >}}<br>
➡️1'000'000'000b / 800 = <b>125'000KB</b>
<p></p>
{{< hl >}}How many bits are in a Mebibyte?{{< /hl >}}<br>
➡️1'048'576B * 8 = <b>8’388’608b</b>
<p></p>
{{< hl >}}You buy an HDD advertised with 1TB. How much usable space will the Windows operating system report you and why?{{< /hl >}}<br>
➡️If you have a 1TB HDD in your PC, then you have a real storage of 932GB. This is because the computer is working with binary numbers (1,024 bytes = 1kb).
<p></p>
{{% callout note %}}
  5. <b>Task – Decode the following binary sequences to text. Each character uses 8-bits.</b>
{{% /callout %}}
{{< hl >}}01000001011011010110000101101110011011110111100000100000010101000110010101100001{{< /hl >}}<br>
➡️Amanox Tea<br>
💡You have to read the binary code from the right to the left side. Then you encode the binary digits.<br>
Example: 10101 ➔ (1 * 2^1) + (0 *2^2) + (1 *2^3) + (0 *2^4) + (1 *2^5) = <b>42</b> <br>
After this you can have a look to the ASCII-Table. <b>42</b> corresponds to <b> * </b>.<br>
<p></p>
{{< hl >}}"Xavier" in a binary sequence{{< /hl >}}<br>
➡️01011000 01100001 01110110 01101001 01100101 01110010<br>
<p></p>
{{% callout note %}}
  4. <b>Task – Multiplication with basic instructions<br>
  Create a sequence in the Johnny simulator that takes 2 numbers from any 2 registers, multiplies them and writes the result to another register.
</b>
{{% /callout %}}
<p></p>

## {{< hl >}}Johny Simulator{{< /hl >}}<br>

> The Johny Simulator shows us, how a RAM calculation is working. Additions and subtractions can be performed directly, while multiplications have to be added up over several steps. In the simulator you have the opportunity to write and simulate programms.<br> Here is a list of the program commands:<br>
● `TAKE` The value of the location (given by the absolute address) is transported to
the accumulator.<br>
● `SAVE` The value of the accumulator is transported to the location given by the absolute
address.<br>
● `ADD` The value of a location (given by the absolute address) is added to the value
in the accumulator.<br>
● `SUB` The value of a location (given by the absolute address) is subtracted from the
value in the accumulator.<br>
● `INC` The value of the location (given by the absolute address) is incremented.<br>
● `DEC` The value of the location (given by the absolute address) is decremented.<br>
● `NULL` The value of the location (given by the absolute address) is set to zero.<br>
● `TST` If and only if the location (given by the absolute address) has a zero value,
the next macro instruction is skipped.<br>
● `JMP` The program is continued at the given location.<br>
● `HLT` The simulator shows a message that the program is finished.<br>
<p></p>

Example programm for a multiplication <b>8 * 5 = 40</b><br>
<p></p>
| Adress | Data | Data type |
|--------|------|-----------|
| 020    | 8    | Factor    |
| 021    | 5    | Factor    |
| 022    | 40   | Product   |<br>
<p></p>

1.   

![Johny](johny.jpg "<b>Johny Simulator</b> (Screenshot)")<br>
