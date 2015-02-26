
# Build the "core libraray" for compiling arduino on Edison
#board = "Galileo Gen2"
#board = "Galileo"
board = "Edison"

options = "-m32 -march=i586 -c -g -Os -w -fno-exceptions -ffunction-sections -fdata-sections -MMD -D__ARDUINO_X86__ -Xassembler -march=i586 -m32 -DARDUINO=153"
output = "-Os -Wl,--gc-sections -march=i586"

if board == "Edison":
    options = "-m32 -march=i586 -c -g -Os -w -fno-exceptions -ffunction-sections -fdata-sections -MMD -D__ARDUINO_X86__ -march=i686 -m32 -DARDUINO=153"
    includes = ['hardware/arduino/edison/cores/arduino', 'hardware/arduino/edison/variants/edison_fab_c']
    libPath = [Glob('hardware/arduino/edison/cores/arduino/*.c*'), 'hardware/arduino/edison/variants/edison_fab_c/variant.cpp']
    output = '-m32 -march=i586 --sysroot=hardware/tools/edison/sysroots/core2-32-poky-linux -Os -Wl,--gc-sections -march=i686'
elif board == "Galileo":
    includes = ['hardware/arduino/x86/cores/arduino', 'hardware/arduino/x86/variants/galileo_fab_d']
    libPath = [Glob('hardware/arduino/x86/cores/arduino/*.c*'), 'hardware/arduino/x86/variants/galileo_fab_d/variant.cpp']
elif board == "Galileo Gen2":
    includes = ['hardware/arduino/x86/cores/arduino', 'hardware/arduino/x86/variants/galileo_fab_g']
    libPath = [Glob('hardware/arduino/x86/cores/arduino/*.c*'), 'hardware/arduino/x86/variants/galileo_fab_g/variant.cpp']
    



env = Environment(CPPPATH = includes, CCFLAGS=options)
#print Glob('arduino/edison/cores/arduino/*.c*')
env.Library('core', libPath)
env.Program('sketch.elf', ['blink.cpp', 'libcore.a'], CCFLAGS=output, LIBS=['pthread', 'm'])
