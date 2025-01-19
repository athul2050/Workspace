Certainly! Below is a step-by-step guide to creating a **subVI** in **LabVIEW** that multiplexes four inputs into a single output based on a selection control.

---

## **Steps to Create the SubVI:**

### **Step 1: Create a New VI**
1. Open **LabVIEW**.
2. Create a new **VI** by selecting **File** → **New VI**.
3. Open the **Block Diagram** by selecting **Window** → **Show Block Diagram**.

---

### **Step 2: Add Controls and Indicators**
1. In the **Front Panel**, add the following controls:
   - **Four Numeric Controls** (Floating-Point):
     - Rename them as **In1**, **In2**, **In3**, and **In4**.
   - **One Unsigned 8-bit Integer Control**:
     - Rename it as **Select**.
   - **One Numeric Indicator** (Floating-Point):
     - Rename it as **Out**.

2. Arrange the controls neatly on the **Front Panel**.

---

### **Step 3: Implement the Multiplexer Logic in the Block Diagram**
1. **Navigate to the Block Diagram**.
2. **Add a Case Structure**:
   - From the **Functions Palette**, go to:
     ```
     Programming → Structures → Case Structure
     ```
   - Place the **Case Structure** on the Block Diagram.
   - Connect the **Select** control to the **Case Selector** input.

3. **Create Cases for Each Selection Value**:
   - Add **four cases** (`1`, `2`, `3`, and `4`).
   - Inside each case, wire the corresponding input to the output:
     - **Case 1**: Wire **In1** to **Out**.
     - **Case 2**: Wire **In2** to **Out**.
     - **Case 3**: Wire **In3** to **Out**.
     - **Case 4**: Wire **In4** to **Out**.
   - For any **default case**, you can set the output to `0` or any desired value.

---

### **Step 4: Create the SubVI**
1. Select all the elements in the **Block Diagram**.
2. From the **Edit menu**, choose **Create SubVI**.
3. This will automatically generate a subVI that you can use in other programs.
4. Save the subVI with a meaningful name, such as **Multiplexer_SubVI.vi**.

---

### **Step 5: Testing the SubVI**
1. Open the **Top-Level VI** where you want to use this subVI.
2. Place the **Multiplexer SubVI** inside the **Block Diagram**.
3. Provide test inputs (`In1`, `In2`, `In3`, `In4`) and change the **Select** value to verify the correct output.

---

## **Alternative Approach Using the Select Function**
Instead of a **Case Structure**, you can use the **Select Function**:
1. From the **Functions Palette**, go to:
   ```
   Programming → Comparison → Select
   ```
2. Use a **nested Select** approach:
   - First **Select Function**: Chooses between `In1` and `In2` (if `Select` is `1` or `2`).
   - Second **Select Function**: Chooses between `In3` and `In4` (if `Select` is `3` or `4`).
   - A final **Select Function**: Chooses between the results of the first two.
3. This approach avoids a **Case Structure** but requires three **Select Functions**.

---

### **Final Thoughts**
- The **Case Structure** method is more readable.
- The **Select Function** method is compact and efficient.
- The subVI can now be used in multiple VIs, making your program modular.

Would you like a screenshot of the block diagram or a LabVIEW file? 🚀
