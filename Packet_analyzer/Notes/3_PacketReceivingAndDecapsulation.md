Perfect—this is the **other half of the story** and very important for interviews 👍

Let’s understand how packets are **received and converted back to original data**.

---

## 🔹 What happens at the receiver? (Decapsulation)

When packets reach the destination, the process is **reversed**. This is called **decapsulation**.

---

## 🔹 Step-by-step process

### 1. **Physical Layer (Bits received)**

* Signals (electrical/radio) are received
* Converted back into **binary data (bits)**

---

### 2. **Data Link Layer → Frame processing**

* Bits are grouped into **frames**
* Checks:

  * MAC address (is it for me?)
  * Error detection (FCS)

👉 If valid → remove frame header/trailer
👉 Pass remaining data upward

---

### 3. **Network Layer → Packet processing**

* Extract **IP packet**
* Checks:

  * Destination IP address
  * TTL validity

👉 Removes IP header
👉 Passes data to transport layer

---

### 4. **Transport Layer → Segment processing**

* Gets **segments**
* Based on protocol:

#### ✔ TCP:

* Reorders packets using **sequence numbers**
* Detects missing packets
* Requests retransmission (if needed)
* Ensures **reliable delivery**

#### ✔ UDP:

* No ordering, no retransmission
* Faster but less reliable

👉 Removes transport header
👉 Passes clean data upward

---

### 5. **Application Layer → Final data**

* Data is delivered to:

  * Browser (HTTP)
  * App (chat, file, etc.)

👉 User finally sees:

* Webpage
* Message
* File

---

## 🔹 Flow Summary (Reverse Process)

```id="y10xar"
Bits (Physical Layer)
   ↑
Frame (Data Link Layer)
   ↑
Packet (Network Layer)
   ↑
Segment (Transport Layer)
   ↑
Data (Application Layer)
```

---

## 🔹 Key Concept: Decapsulation

* Each layer **removes its own header**
* Gradually retrieves original data

---

## 🔹 Important Interview Points

* **Reassembly happens at Transport Layer (TCP)**
* **Sequence numbers** ensure correct order
* **Checksum** ensures data integrity
* **TCP vs UDP difference is critical**

---

## 🔹 Simple Analogy

Receiving courier parcels:

* Receive boxes (frames)
* Open box → get envelope (packet)
* Open envelope → get pages (segment)
* Arrange pages → original book (data)

---

## 🔹 One-line answer (interview ready)

> At the receiver, packets undergo decapsulation where each layer removes its header, and the transport layer reassembles segments to reconstruct the original data.

---

If you want, I can give you a **full end-to-end example (browser → server → browser)** which is often asked in networking/5G interviews.
