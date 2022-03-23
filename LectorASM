'''
Programa que lee archivos ASM y retorna arreglos conversos en hexa.
'''

#!/usr/bin/python
from binascii import *
import sys

files = {}
length = []

def write(string):
 sys.stdout.write(string)

def process_file(file):
 source = open(file,"rb")
 write("char shellcode[]=\n\t\t")
 i = 1
 l = 0
 write("\"")
 for data in source.read():
  write("\\x")
  write(b2a_hex(data))
  if (i % 15)==0:
   write("\"\n\t\t\"")
  i+=1
  l+=1
 files[file[0:-4]]= l
 write("\";\n\n")
 source.close()

print("HDL Shellcode Lab - Bin to C")
if(len(sys.argv)<2):
 exit(0)
process_file(sys.argv[1])
