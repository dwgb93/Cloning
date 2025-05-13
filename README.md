# Cloning
Instructions to clone a new hard drive.

Absolutely! Here's a **step-by-step guide to clone your existing Windows 10 hard drive to your new SATA SSD** using **Macrium Reflect Free**, one of the most reliable and user-friendly tools available:

---

## ✅ Prerequisites

### Hardware:

* New SATA SSD installed and connected (internally or via USB-to-SATA adapter).
* Your current hard drive still functioning.

### Software:

* [Download Macrium Reflect Free](https://www.macrium.com/reflectfree)

---

## 🛠 Step-by-Step Cloning Process

### **Step 1: Install Macrium Reflect Free**

1. Download and install from: [https://www.macrium.com/reflectfree](https://www.macrium.com/reflectfree)
2. Run the software and allow it to scan your drives.

---

### **Step 2: Prepare for Cloning**

1. **Backup important data** just in case. Even though cloning is low-risk, it’s wise to be cautious.
2. Make sure the SSD is **unallocated** (i.e., no partitions on it). If it has any partitions, delete them using:

   * Disk Management (`Win+X → Disk Management`) or
   * Macrium Reflect's partition tools.

---

### **Step 3: Start the Clone Process**

1. In Macrium Reflect:

   * Your current system disk (HDD) should show up at the top.
   * Click **“Clone this disk...”** under your current HDD.

2. In the wizard:

   * Select your **new SSD** as the **destination disk**.
   * Click **“Select a disk to clone to…”** and choose your SSD.

3. If the SSD is smaller than the HDD:

   * Manually drag the partitions one-by-one from the source to the destination and **resize** the main partition (usually C:) to fit.

4. Confirm the partition layout looks good.

---

### **Step 4: Begin Cloning**

1. Click **“Next”** → then **“Finish”**.
2. You can uncheck the option to save the backup as an XML file.
3. Click **“OK”** to start the clone.
4. Wait for the process to complete (can take 15 minutes to over an hour depending on disk size/speed).

---

### **Step 5: Boot from SSD**

1. Shut down the computer once cloning completes.
2. Disconnect the **old HDD** (physically unplug the SATA or power cable), or enter BIOS and set the **SSD as the first boot device**.
3. Boot into Windows — it should look exactly the same but now running from the SSD.

---

### **Step 6: Verify & Cleanup**

1. Once verified everything works, you can:

   * Wipe the old HDD and use it for storage.
   * Or leave it disconnected if you plan to repurpose/dispose of it.

---

## 🧼 Optional Post-Clone Tweaks

* Enable **TRIM** support for SSDs (usually enabled by default on Windows 10).
* Run `Win + R → dfrgui` and turn **off scheduled defragmentation** for the SSD.
* Consider running:

  ```powershell
  fsutil behavior query DisableDeleteNotify
  ```

  Should return `0` (means TRIM is enabled).

---
