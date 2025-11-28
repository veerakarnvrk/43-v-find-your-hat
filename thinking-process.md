# Thinking Process Guidelines

## Table of Contents

- [Thinking Process Guidelines](#thinking-process-guidelines)
  - [Table of Contents](#table-of-contents)
  - [1. Workflow Planning](#1-workflow-planning)
  - [2.1. Board Functions (Hardcoded)](#21-board-functions-hardcoded)
  - [2.2. Board Functions (Generated)](#22-board-functions-generated)
  - [3. Input Functions](#3-input-functions)
  - [4. Movement Functions](#4-movement-functions)
  - [5. Game Rule Functions](#5-game-rule-functions)
  - [6. Game Play Loop](#6-game-play-loop)
- [WRITE YOUR THINKING PROCESS BELOW. ](#write-your-thinking-process-below)

## <span style="font-weight:bold; color: black; background-color: gold; padding: 0.5rem 2rem;">1. Workflow Planning</span>

↳ Draw a flowchart or write steps describing:

<p style="display: flex; align-items: center; gap: 1rem;">
<span style="font-weight:bold; color: wheat; background-color: blue; padding: 0.5rem 2rem; border-radius: 0.5em;">Game start</span>
<span style="color: wheat; font-weight:bold; font-size:2rem; ">→</span>
<span style="font-weight:bold; color: wheat; background-color: blue; padding: 0.5rem 2rem; border-radius: 0.5em;">Read input</span>
<span style="color: wheat; font-weight:bold; font-size:2rem;">→</span>
<span style="font-weight:bold; color: wheat; background-color: blue; padding: 0.5rem 2rem; border-radius: 0.5em;">Update position</span>
<span style="color: wheat; font-weight:bold; font-size:2rem;">→</span>
<span style="font-weight:bold; color: wheat; background-color: blue; padding: 0.5rem 2rem; border-radius: 0.5em;">Check rules</span>
<span style="color: wheat; font-weight:bold; font-size:2rem;">→</span>
<span style="font-weight:bold; color: wheat; background-color: blue; padding: 0.5rem 2rem; border-radius: 0.5em;">End/Continue</span>
</p>

↳ Must include:

- Input/output of each function.
- Edge cases (invalid input, boundaries, hole/hat tiles).

## <span style="font-weight:bold; color: black; background-color: gold; padding: 0.5rem 2rem; margin-top: 1rem; border-buttom: none;">2.1. Board Functions (Hardcoded)</span>

↳ Prints the hardcoded board in terminal.

<span style="font-weight:bold; color: gold;">Thinking process should explain:</span>

- How the board is represented (2D array).
- Tile types (PLAYER, EMPTY, HOLE, HAT).

## <span style="font-weight:bold; color: black; background-color: gold; padding: 0.5rem 2rem;">2.2. Board Functions (Generated)</span>

↳ Creates a random board with player, hat, and holes.
↳ Prints the board in terminal.

<span style="font-weight:bold; color: gold;">Thinking process should explain:</span>

- How the board is represented (2D array).
- Tile types (PLAYER, EMPTY, HOLE, HAT).
- How random placement avoids overlaps.

## <span style="font-weight:bold; color: black; background-color: gold; padding: 0.5rem 2rem;">3. Input Functions</span>

↳ Reads and validates user input (w, a, s, d).
↳ Logs invalid input.

<span style="font-weight:bold; color: gold;">Thinking process should explain:</span>

- Input/output.
- Edge cases (invalid input, boundaries).
- How player position is updated.

## <span style="font-weight:bold; color: black; background-color: gold; padding: 0.5rem 2rem;">4. Movement Functions</span>

↳ Updates playerRow / playerCol based on the move.

<span style="font-weight:bold; color: gold;">Thinking process should explain:</span>

- Input/output.
- Edge cases (invalid input, boundaries).
- How player position is updated.

## <span style="font-weight:bold; color: black; background-color: gold; padding: 0.5rem 2rem;">5. Game Rule Functions</span>

↳ Checks for out-of-bounds, falling into a hole, or finding the hat.

<span style="font-weight:bold; color: pink;">&nbsp;Game Rules:&nbsp;</span>

- Wins by finding the hat.
- Loses by landing in a hole.
- Loses by moving outside the board.

<span style="font-weight:bold; color: gold;">Thinking process should explain:</span>

- How to determine win/loss conditions.
- Handling messages for win/loss conditions.

## <span style="font-weight:bold; color: black; background-color: gold; padding: 0.5rem 2rem;">6. Game Play Loop</span>

↳ Combine all functions into a playable loop.
↳ Ensure messages appear correctly, board prints at start, and invalid input is handled.

<span style="font-weight:bold; color: gold;">Thinking process should explain:</span>

- How to determine win/loss conditions.
- Handling messages for win/loss conditions
- How to update the board when the player moves.

---

# <p style="display: flex; align-items: center; gap: 0.5em;"><span style="font-weight:bold; color: white; background-color: lightSeaGreen; padding: 0.5rem 2rem;">WRITE YOUR THINKING PROCESS BELOW.</span><span style="font-weight:bold; color: white; background-color: lightSeaGreen; padding: 0.5rem 0;">&nbsp;</span></p>

<!-- Thinking Process -->
<!-- 1. Workflow Planning -->
<!-- 2.1. Board Functions (Hardcoded) -->
<!-- 2.2. Board Functions (Generated) -->
<!-- 3. Input Functions -->
<!-- 4. Movement Functions -->
<!-- 5. Game Rule Functions -->
<!-- 6. Game Play Loop -->

[Back to Table of Contents](#table-of-contents)

---------------------------------------------------------------------------------------------------------------------

1. Workflow Planning
  ขั้นตอนการเตรียมการ
    - กำหนดสัญญลักษณ์ก่อน เช่น * แทนผู้เล่น, ^ แทน หมวก, O แทน หลุม
    - สร้างแผนที่ ที่สุ่มวางหมวกและหลุมไว้เรียบร้อยแล้ว
    - เริ่มเกม มีวัตถุทุกอย่างพร้อมให้เล่น
    - เริ่มวนรอบ เข้าสู่ฟังก์ชันหลักที่ใช้ในการควบคุมการเล่นเกม
  ขั้นตอนวนรอบการเล่น (ขั้นตอนนี้จะทำซ้ำจนกว่าจะจบเกม)
    - แสดงแผนที่ปัจจุบัน myField.print() แผนที่โชว์บนหน้าจอ Terminal
    - รับคำสั่งจากผู้เล่น const direction = prompt(...) ทิศทางการเดิน (w/a/s/d)
    - ประมวลผลการเดิน myField.move(direction) คำนวณตำแหน่งใหม่ (newX, newY)
    - ตรวจสอบสถานะ myField.move(ภายใน if blocks) ตรวจสอบว่าตำแหน่งใหม่คือ 1.ตกขอบ? 2.หลุม? 3.หมวก?
    - อัปเดตแผนที่ myField.move หากยังไม่แพ้/ชนะ ตำแหน่งเก่าเปลี่ยนเป็น PATH() และผู้เล่นจะย้ายไปตำแหน่งใหม่
    - วนกลับไปเริ่มต้น while (true) วนกลับไปที่ขั้นตอนแรก (แสดงแผนที่)
  จุดสิ้นสุด Worlkflow จะสิ้นสุดก็ต่อเมื่อ
    - เงื่อนไข	                ข้อความที่แสดง	                   การทำงานในโค้ด
      แพ้ (ตกขอบ)	      "คุณเดินตกขอบแผนที่! Game over T^T"	       process.exit()
      แพ้ (ตกหลุม)	     "คุณเดินตกหลุม! Game over T^T"	           process.exit()
      ชนะ (เจอหมวก)	   "คุณหาหมวกเจอแล้ว! ชนะแล้ว เย้!"	          process.exit()


2.1 Board Functions (Hardcoded)
  ส่วนที่เป็น Hardcoded หลักๆ ในโค้ดเกมนี้คือค่าคงที่ (Constants) และขนาดเริ่มต้น, เปอร์เซ็นต์หลุม ที่กำหนดไว้ตายตัวตั้งแต่แรก
    const PLAYER = "*";
    const EMPTY = "░";
    const HOLE = "O";
    const HAT = "^";
    const PATH = " ";


2.2 Board Functions (Generated)
  ส่วนของโค้ดที่ถือเป็น Board Functions คือ static generateField ที่อยู่ในคลาส Field
    - const field = Array(height).fill(null).map(() => Array(width).fill(EMPTY));
    สร้างโครงสร้างหลักของแผนที่ขนาดที่กำหนด (height x width) แล้วเติมด้วยสัญลักษณ์ พื้นที่ว่าง (EMPTY,░) ทั้งหมด

    - const hatY = Math.floor(Math.random() * height); ... field[hatY][hatX] = HAT;
    สุ่มตำแหน่ง (X, Y) และวางหมวก (HAT, ^) ซึ่งเป็นเป้าหมายของผู้เล่น

    - const numHoles = Math.floor(height * width * (percentage / 100));
    คำนวณจำนวนหลุมที่ต้องการตามสัดส่วนของ percentage ที่กำหนด

    - for (let i = 0; i < numHoles; i++) { ... } while (field[holeY][holeX] !== EMPTY); field[holeY][holeX] = HOLE;วนลูปเพื่อสุ่มตำแหน่งของหลุม (HOLE, O) โดยมีเงื่อนไขว่าต้องวางในตำแหน่งที่ยังเป็นพื้นที่ว่างอยู่เท่านั้น(ป้องกันการวางทับหมวกหรือหลุมอื่น)

    - return field;
    คืนค่าแผนที่ที่เป็น Array 2 มิติ ที่สร้างและเตรียมพร้อมสำหรับการเริ่มเกม


3. Input Functions
  - const prompt = promptSync({ sigint: true });
    ส่วนนี้เป็นการ import และกำหนดตัวแปร prompt ให้เป็นฟังก์ชันที่ใช้รับ input จากผู้ใช้ใน Node.js (โดยใช้ไลบรารี prompt-sync)

  - const direction = prompt("Which way? (w/a/s/d): ");
  ส่วนนี้คือบรรทัดที่เรียกใช้ฟังก์ชัน prompt จริงๆ เพื่อแสดงข้อความ "Which way? (w/a/s/d): " และรอรับ input เป็นทิศทางการเคลื่อนที่จากผู้ใช้ และจะถูกเก็บไว้ในตัวแปร direction


4. Movement Functions
  - move(direction) {
        let newX = this.playerX;
        let newY = this.playerY;
        
        switch (direction) {
            case "w":
                newY -= 1;
                break;
        }

        if (this.isOutOfBounds(newX, newY)) {
        }

        if (this.field[newY][newX] === HOLE) {
        }
        if (this.field[newY][newX] === HAT) {
        }

        this.field[this.playerY][this.playerX] = PATH;
        this.playerX = newX;
        this.playerY = newY;
        this.field[this.playerY][this.playerX] = PLAYER;
    }

    หน้าที่หลัก:
    รับทิศทาง (w, a, s, d) จากผู้ใช้
    คำนวณตำแหน่งใหม่ (newX, newY)
    ตรวจสอบว่าตำแหน่งใหม่อยู่นอกขอบเขตหรือไม่โดยเรียกใช้ this.isOutOfBounds()
    ตรวจสอบว่าตำแหน่งใหม่คือหลุม (HOLE) หรือหมวก (HAT) เพื่อตัดสินผลของเกม
    หากทุกอย่างเรียบร้อย จะทำการอัปเดตแผนที่โดยย้ายสัญลักษณ์ผู้เล่น (PLAYER) ไปยังตำแหน่งใหม่และทิ้งร่องรอย (PATH) ไว้ที่ตำแหน่งเดิม


5. Game Rule Functions
  - Losing Rule (ตกขอบแผนที่)
  if (this.isOutOfBounds(newX, newY)) {
    console.log("คุณเดินตกขอบแผนที่! Game over T^T");
    process.exit();
  }
  Rule ผู้เล่นแพ้ทันทีเมื่อเดินออกนอกขอบเขตของแผนที่
  Function ใช้เมธอด isOutOfBounds() เพื่อตรวจสอบเงื่อนไขนี้

  - Losing Rule (ตกหลุม)
  if (this.field[newY][newX] === HOLE) {
    console.log("คุณเดินตกหลุม! Game over T^T");
    process.exit();
  }
  Rule ผู้เล่นแพ้ทันทีเมื่อเดินตกหลุม (HOLE, O)

  - Winning Rule (เจอหมวก)
  if (this.field[newY][newX] === HAT) {
    console.log("คุณหาหมวกเจอแล้ว! ชนะแล้ว เย้!");
    process.exit();
  }
  Rule ผู้เล่นชนะทันทีเมื่อหาหมวกเจอ (HAT, ^)


6. Game Play Loop
  - ฟังก์ชัน gameLoop() นี้ทำหน้าที่วนซ้ำการทำงานหลักของเกมอย่างไม่มีที่สิ้นสุด จนกว่าจะเกิดเงื่อนไขการชนะหรือแพ้ภายในเมธอด move() ซึ่งจะเรียก process.exit() เพื่อจบโปรแกรม
        function gameLoop() {
          while (true) { // <-- ลูปที่ทำงานไปเรื่อย ๆ
              myField.print(); // 1. แสดงสถานะปัจจุบันของแผนที่
              const direction = prompt("Which way? (w/a/s/d): "); // 2. รับ input จากผู้เล่น
              myField.move(direction); // 3. ประมวลผลการเคลื่อนที่และตรวจสอบกฎของเกม
            }
        }
        gameLoop(); // <-- เริ่มต้นลูป