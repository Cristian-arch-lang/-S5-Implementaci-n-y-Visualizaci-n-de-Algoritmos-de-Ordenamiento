import random
import time
import tkinter as tk
from tkinter import ttk

# Algoritmos de Ordenamiento
def bubble_sort(arr, draw, delay):
    n = len(arr)
    for i in range(n):
        swapped = False
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
                draw(arr, ["red" if x == j or x == j + 1 else "blue" for x in range(len(arr))])
                time.sleep(delay)
        if not swapped:
            break

def selection_sort(arr, draw, delay):
    n = len(arr)
    for i in range(n):
        min_idx = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
        draw(arr, ["red" if x == i or x == min_idx else "blue" for x in range(len(arr))])
        time.sleep(delay)