# **Implementasi Struktur Data Linked List (Python)**

Dokumen ini memberikan penjelasan mengenai cara kerja dan implementasi dasar **Linked List** menggunakan Python.  
Struktur ini tersusun dari node yang saling terhubung, di mana setiap node menyimpan data dan alamat ke node berikutnya.

---

## **1. Node**

Node adalah komponen utama Linked List. Setiap node memiliki dua bagian:

- `data`: nilai yang disimpan
- `next`: referensi ke node berikutnya

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
```

---

## **2. Kelas LinkedList**

`LinkedList` berfungsi sebagai wadah untuk node-node tersebut dan menyimpan penunjuk ke elemen pertama (head).

```python
class LinkedList:
    def __init__(self):
        self.head = None
```

---

## **2.1 Menambah Elemen di Awal (insert_at_first)**

Metode ini memasukkan data sebagai elemen pertama dalam list.

```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node
```

---

## **2.2 Menambah Elemen di Akhir (insert_at_last)**

Digunakan untuk memasukkan data ke posisi paling belakang Linked List.

```python
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next

        node = Node(data)
        node_sekarang.next = node
```

---

## **2.3 Menyisipkan Data pada Posisi Tertentu (insert_at)**

Menambahkan elemen pada index tertentu dalam list.

```python
def insert_at(self, index, data):
    if index < 0 or index > self.length() - 1:
        print("indeks tidak valid")
    elif index == 0:
        self.insert_at_first(data)
    else:
        urutan = 0
        node_sekarang = self.head

        while urutan < index - 1:
            urutan += 1
            node_sekarang = node_sekarang.next

        node = Node(data, node_sekarang.next)
        node_sekarang.next = node
```

---

## **2.4 Menampilkan Isi Linked List (print)**

Metode ini menelusuri node dari awal hingga akhir dan menampilkannya.

```python
def print(self):
    if self.head is None:
        print("data kosong")
    else:
        text_print = ''
        node_sekarang = self.head

        while node_sekarang:
            text_print += str(node_sekarang.data) + "→"
            node_sekarang = node_sekarang.next

        print(text_print)
```

---

## **2.5 Menghitung Jumlah Node (length)**

```python
def length(self):
    urutan = 0
    data_sekarang = self.head

    while data_sekarang:
        data_sekarang = data_sekarang.next
        urutan += 1

    return urutan
```

---

## **3. Contoh Penggunaan Program**

```python
ll = LinkedList()
ll.insert_at_first("jeruk")
ll.insert_at_first("mangga")
ll.insert_at_first("manggis")
ll.insert_at_last("apel")
ll.insert_at(2, "durian")

ll.print()
print(ll.length())
```

---

