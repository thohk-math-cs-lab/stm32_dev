stm32_dev/
├─ README.md              # goal, hardware facts, how to build/flash
├─ lab-notes.md           # per plan: versions, observations, evidence per MVP
├─ docs/
│  ├─ RM0090 (stm32f429 reference) notes/   # or links
│  ├─ nucleo-144-manual-notes.md           # LED/UART pin tables
│  └─ clock-tree.md       # filled in at MVP 7
├─ vendor/
│  └─ bare-metal-programming-guide/   # git submodule, read-only checkpoints
└─ steps/
   ├─ mvp1-boot/          # ← start here now
   │  ├─ main.c           # vector table, _reset(), main()
   │  ├─ link.ld
   │  ├─ Makefile         # includes: flash: st-flash target
   │  └─ EVIDENCE.md      # objdump -h output, st-flash logs
   ├─ mvp2-blinky/        # copied forward from mvp1, then extended
   │  ├─ main.c           # + struct gpio, PIN(), gpio_set_mode/write, spin()
   │  ├─ link.ld
   │  ├─ Makefile
   │  └─ EVIDENCE.md
   ├─ mvp3-systick/       # mcu.h emerges here (gpio/systick/uart structs)
   ├─ mvp4-uart/          # + uart struct, boot banner
   ├─ mvp5-printf/        # + output hook, log macros
   ├─ mvp6-cmsis/         # vendor headers, diff report vs mvp5
   ├─ mvp7-clock/         # clock profiles, recomputed BRR/SysTick
   └─ mvp8-webserver/     # ethernet, DHCP, dashboard, threat model