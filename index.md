import serial
import time
ser = serial.Serial('COM4', 9800)
time.sleep(2)

user_input1 = 'L'
while user_input1 != 'q':
    user_input1 = input('Y = Yellow Light, R = Red Light, G = Green Light, q = quit :'  )
    if user_input1 == 'Y':
        user_input2 = input('H = on, L = off, q = quit :'  )
        if user_input2 == 'H':
            user_input2 = 'S'
        byte_command = user_input2.encode()
        ser.write(byte_command)   # send a byte
        time.sleep(0.5) # wait 0.5 seconds
    if user_input1 == 'R':
        user_input2 = input('H = on, L = off, q = quit :'  )
        if user_input2 == 'H':
            user_input2 = 'K'
        byte_command = user_input2.encode()
        ser.write(byte_command)   # send a byte
        time.sleep(0.5) # wait 0.5 seconds
    if user_input1 == 'G':
        user_input2 = input('H = on, L = off, q = quit :'  )
        byte_command = user_input2.encode()
        ser.write(byte_command)   # send a byte
        time.sleep(0.5) # wait 0.5 seconds

print('q entered. Exiting the program')
ser.close()
