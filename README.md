# multithreding
multithreadingexamples
---------------------------------------------------------------------------------------
import threading
import time
<br>

def square(lst):
    for val in lst:
       print("{} square of number in list{}---->:{}".format(threading.current_thread().name,val,val**2))
       time.sleep(4)

def cubes(lst):
    for val in lst:
       print("{} cubers of number in list{}---->:{}".format(threading.current_thread().name,val,val**3))
       time.sleep(6)
#main program
bt=time.time()
print("\t program execution started{}".format(threading.current_thread().name))
lst=[12,3,-4,9,19,25,14,17,8]
t=threading.Thread(target=square,args=(lst,))
t.name="sai"
print("-"*40)
lst=[12,3,-4,9,19,25,14,17,8]
t1=threading.Thread(target=cubes,args=(lst,))
t1.name="nav"
t.start()
t1.start()
t.join()
t.join()


print("\t program execution ended ={}".format(threading.current_thread().name))
et=time.time()
print("\t proram excecution time{}".format(et-bt))

