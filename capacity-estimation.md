# Capacity Estimation Report

## 1. User Estimations (DAU & MAU)
- **Total Registered Users**: 2,000
- **Daily Active Users (DAU)**: 500 users/day (~25% of total users)
- **Monthly Active Users (MAU)**: 1,200 users/month (~60% of total users)
- **Peak Concurrent Users**: 200 users (~10% of total users)

---

## 2. Throughput Calculation (Transactions Per Second - TPS)
Throughput is based on user actions such as logins, book searches, borrow/return transactions, and notifications.

### **Assumptions:**
- A DAU of 500 users generates transactions throughout the day.
- Each user performs an average of **10 actions per day** (search, borrow, return, login, etc.).
- System runs for **16 active hours/day** (~57,600 seconds).

### **Total Requests Per Day**
Total Requests = DAU × Avg Requests per User

500 × 10 = 5,000 requests/day

### **Average Throughput (TPS)**
Average TPS = Total Requests / Active Seconds per Day

= 5,000 / 57,600 ≈ 0.09 TPS (low load)

### **Peak Throughput (TPS)**
- **Peak occurs** when 200 concurrent users are active.
- If each user performs **1 action every 2 minutes**, then:

  Peak TPS = 200 / 120 = 1.67 TPS

- **Normal Load TPS**: ~0.1 TPS
- **Peak Load TPS**: ~1.5 - 2 TPS
- **Worst-Case Scenario**: **5 TPS** (mass logins, book reservations, and notifications at the same time)

---

## 3. Read vs Write Operations
This is a **read-heavy system (~80% reads, 20% writes).**

| Operation         | Frequency (per day) | Read/Write Ratio |
|------------------|------------------|----------------|
| **User Logins**      | 500/day         | **100% Read** |
| **Book Searches**    | 2,500/day       | **100% Read** |
| **Borrow Requests**  | 500/day         | **80% Write, 20% Read** |
| **Return Requests**  | 500/day         | **80% Write, 20% Read** |
| **Fines & Payments** | 100/day         | **90% Write, 10% Read** |
| **Notifications**    | 1,000/day       | **100% Write** |

### **Peak Read & Write TPS**
- **Peak Read TPS**: ~2 TPS
- **Peak Write TPS**: ~0.5 TPS

---