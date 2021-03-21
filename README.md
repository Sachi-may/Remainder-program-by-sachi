# Remainder-program-by-sachi
from pygame import mixer
from datetime import *
from time import *

def functio1(file,stopper):
    mixer.init()
    mixer.music.load(file)
    mixer.music.play()
    while True:
        user_input=input()
        if(user_input==stopper):
            mixer.music.stop()
            break
def forlog(mes):
    with open("logs.txt","a") as file:
        file.write(f"{mes} {datetime.now()}\n")

ti_water=time()
ti_eyes=time()
ti_exercise=time()
w=15
e=20
ex=30

while True:
    if time() - ti_water > w:
        print("Its your time to drink . For drinking done the music enter drinking done")
        functio1("water.mp3","drinking done")
        forlog(f"Drank water at")
        ti_water=time()
    if time() - ti_eyes > e:
        print("Its your time for eyes exercise . if exercise of the eye is done to stop the music enter eye ex done")
        functio1("eyes.mp3", "eye ex done")
        forlog(f"eyes exercise  at")
        ti_eyes = time()
    if time() - ti_exercise > ex:
        print("Its your time to physical exercise . After exercise to stop the music enter ex done")
        functio1("exercise.mp3", "ex done")
        forlog(f"exercise at at")
        ti_exercise = time()
        n = input("press q to end the whole program\n")
        if (n == "q"):
            break
