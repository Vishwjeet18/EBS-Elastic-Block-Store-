# EBS-Elastic-Block-Store-



---

## **1. What is EBS?**

* **Elastic Block Store** = **persistent storage** for EC2.
* Works like the **C: drive** or **D: drive** in a computer, but in the cloud.
* Keeps your data safe even if you **stop or restart** your EC2 instance (unless you explicitly delete the volume).

---

## **2. Key Features**

* **Block storage** → Reads/writes small chunks of data (like a hard disk).
* **Persistent** → Data stays even if instance stops.
* **Scalable** → Can resize without downtime.
* **Types** → SSD (fast) & HDD (cheap, big capacity).
* **Snapshots** → Backups stored in S3.
* **Attach/Detach** → Can move between EC2 instances.

---

## **3. How EBS Works**

1. You launch an EC2 → AWS automatically attaches a **root EBS volume** (OS disk).
2. You can add **extra EBS volumes** for data storage.
3. EBS volumes live in **one Availability Zone (AZ)** → must attach to EC2 in the same AZ.
4. You can take **snapshots** and restore them anytime.

---

## **4. Common EBS Types**

| Type      | Use Case                                     | Speed     |
| --------- | -------------------------------------------- | --------- |
| gp3 / gp2 | General-purpose SSD (web apps, boot volumes) | Fast      |
| io2 / io1 | Provisioned IOPS SSD (databases)             | Very fast |
| st1       | Throughput optimized HDD (big data, logs)    | Medium    |
| sc1       | Cold HDD (archival)                          | Slow      |

---

## **5. Basic EBS Commands (AWS CLI)**

```bash
# List volumes
aws ec2 describe-volumes

# Create volume
aws ec2 create-volume --availability-zone us-east-1a --size 10 --volume-type gp3

# Attach volume
aws ec2 attach-volume --volume-id vol-1234567890 --instance-id i-1234567890 --device /dev/sdf

# Detach volume
aws ec2 detach-volume --volume-id vol-1234567890
```

---

## **6. EBS in Real Life**

* Imagine **EC2 is your computer**.
* **EBS is your hard drive**.
* **Snapshot is like taking a backup to an external drive**.

---

If you want, I can also explain **how to add an extra EBS volume to a Windows Server EC2** — that’s closely related to your IIS setup steps earlier. That would cover **create → attach → format → use** inside RDP.
Do you want me to prepare that next?
