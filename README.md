# BDCOM-OLT
BDCOM EPON OLT (P3608B/P3616/P3310D) basic configuration through CLI
How To Delete Onu In BDCOM OLT
প্রথমে আপনাকে OLT তে লগিন করতে হবে।

তারপর Enable mode এ যেতে হবে। এজন্য আপনাকে লগিন এর পর enable লিখে Enter দিলে enable mode এ চলে যাবেন। এখন আপনাকে configure mode এ যেতে হবে, তার জন্য আপনাকে এখন config লিখে Enter দিতে হবে।

এরপর আপনাকে Epon সিলেক্ট করতে হবে, তার জন্য আপনাকে কমান্ড লিখতে হবে interface epon ( epon number ) as like interface epon 0/2 .

তারপর no কমান্ড দিয়ে onu number দিতে হবে, এজন্য আপনাকে কমান্ড লিখতে হবে no epon bind-onu sequence ( onu number )

তারপর অবশ্যই আপনাকে সেভ করার জন্য সেভ কমান্ড দিতে হবে, না হলে OLT Restart হওয়ার পর আবার আগের কনফিগারে ফিরে আসবে। সেভ দাওয়ার জন্য epon থেকে exit কমান্ড দিয়ে বের হতে হবে। তারপর write all লিখে Enter দিলে সেভ হয়ে যাবে।

OLT#enable
OLT#config

OLT_config#interface epoN 0/2

OLT_config_epon0/2#no epon bind-onu sequence 52

OLT_config_epon0/2#exit
OLT_config#write all
---

### ✅ **Batch Deletion of ONU Bindings (1–64)**

#### Example CLI Session (on `epon 0/2`):

```plaintext
enable
config
interface epon 0/2
```
Then you can paste the full list:

```plaintext
no epon bind-onu sequence 1
no epon bind-onu sequence 2
no epon bind-onu sequence 3
no epon bind-onu sequence 4
no epon bind-onu sequence 5
no epon bind-onu sequence 6
no epon bind-onu sequence 7
no epon bind-onu sequence 8
no epon bind-onu sequence 9
no epon bind-onu sequence 10
no epon bind-onu sequence 11
no epon bind-onu sequence 12
no epon bind-onu sequence 13
no epon bind-onu sequence 14
no epon bind-onu sequence 15
no epon bind-onu sequence 16
no epon bind-onu sequence 17
no epon bind-onu sequence 18
no epon bind-onu sequence 19
no epon bind-onu sequence 20
no epon bind-onu sequence 21
no epon bind-onu sequence 22
no epon bind-onu sequence 23
no epon bind-onu sequence 24
no epon bind-onu sequence 25
no epon bind-onu sequence 26
no epon bind-onu sequence 27
no epon bind-onu sequence 28
no epon bind-onu sequence 29
no epon bind-onu sequence 30
no epon bind-onu sequence 31
no epon bind-onu sequence 32
no epon bind-onu sequence 33
no epon bind-onu sequence 34
no epon bind-onu sequence 35
no epon bind-onu sequence 36
no epon bind-onu sequence 37
no epon bind-onu sequence 38
no epon bind-onu sequence 39
no epon bind-onu sequence 40
no epon bind-onu sequence 41
no epon bind-onu sequence 42
no epon bind-onu sequence 43
no epon bind-onu sequence 44
no epon bind-onu sequence 45
no epon bind-onu sequence 46
no epon bind-onu sequence 47
no epon bind-onu sequence 48
no epon bind-onu sequence 49
no epon bind-onu sequence 50
no epon bind-onu sequence 51
no epon bind-onu sequence 52
no epon bind-onu sequence 53
no epon bind-onu sequence 54
no epon bind-onu sequence 55
no epon bind-onu sequence 56
no epon bind-onu sequence 57
no epon bind-onu sequence 58
no epon bind-onu sequence 59
no epon bind-onu sequence 60
no epon bind-onu sequence 61
no epon bind-onu sequence 62
no epon bind-onu sequence 63
no epon bind-onu sequence 64
```

Then exit the EPON interface and **save the configuration**:

```plaintext
OLT_config_epon0/2# exit
OLT_config# write all
```

---

### 🔁 Optional: Bash Script to Generate Commands

If you ever need to regenerate similar commands in bulk, you can use this simple shell script:

```bash
for i in $(seq 1 64); do
  echo "no epon bind-onu sequence $i"
done
```

---

Let me know if you want:

* To **delete from all EPON ports** automatically
* A **text file** or **script version** to upload to your OLT
* The **full configuration for ONU addition**

I'm here to help you streamline your BDCOM OLT management.
