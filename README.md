# Rangkuman-Modul3

Pengurutan / Sorting
Proses pengurutan merupakan salah satu proses yang sangat penting dalam pengolahan data.
Misalkan terdapat data mahasiswa, terkadang dibutuhkan data yang urut berdasarkan nilai, penghasilan orang tua,
sehingga dari data yang urut tersebut dapat diambil keputusan mengenai mahasiswa yang berhak menerima beasiswa.
proses pengurutan data ini dilakukan dengan membandingkan antara data yang satu dengan data yang lain.


Bubble Sort
merupakan proses pengurutan yang secara berangsur-angsur berpindah ke posisi yang tepatkarena itulah dinamakan Bubble
yang artinya gelembung.

Bubble sort mengurutkan data dengan cara sebagai berikut :
  1. data dibaca mulai dari paling kiri atau mulai dari indeks ke 0 (phyton) dari suatu list data
  2. Bandingkan antara dua buah data yang saling berdekatan (antara data ke i dan i+1),
     tukar posisi jika data ke-i lebih besar dibandingkan data ke-i+1 (pengurutan secara ascending)
  3. pindah satu posisi
  4. lakukan perbandingan seperti langkah ke-2 dan pindah satu posisi kembali seperti langkah ke-3.
     Lakukan terus menerus sampai indeks data terakhir.
  5. Setelah langkah ke-4 dilakukan, maka data yang berada di posisi paling kanan (indeks ke-N) adalah data terbesar .
  6. Ulangi lagi langkah 1-4 dimulai dari indeks data ke 0 sampai dengan indeks ke N-1, N-2, ..., 0


code

        def bubbleSort(listData):
            print('Data yang akan diurutkan : ', listData)
            count=0
            for outIter in range(len(listData)-1,-1,-1):
                count=count+1
                print ('Iterasi ke-', count,':')
                for i in range(outIter):
                    if listData[i]>listData[i+1]:
                        temp=listData[i]
                        listData[i]=listData[i+1]
                        listData[i+1]=temp
                        #listData[i],listData[i+1]=listData[i+1],listData[i]
                    print(listData)
            print('Data urut-',listData)
            
          a=[12,0,5,1,11,20,4,2]
          bubbleSort(a)
          b=[12,11,5,1,0]
          print('--')
          bubbleSort(b)
          

Selection Sort
adalah algoritma pengurutan yang sederhana namun sangat efisien dalam penggunaanya.

Berikut tahapan algoritma selection sort (ascending order):
  1. Algoritma ini dimulai dari indeks awal sampai dengan indeks akhir data
  2. Cari data dengan nilai paling minimal (dari indeks awal sampai dengan indeks akhir) melalui proses perbandingan
  3. Letakkan data minimal ini di indeks awal
  4. Ulangi lagi proses pencarian data paling minimal (dari indeks awal+1 sampai dengan indeks akhir, karena indeks awal sudah terisi data yang tepat).
  5. Letakkan data ini pada indeks awal+1
  6. Ulangi lagi proses pencarian data paling minimal (dari indeks awal+2 sampai dengan akhir) dan letakkan data ini pada indeks awal+2, dst.
  
  
contoh kode

    def selectionSort(listData):
        print('Algoritma Selection Sort konvensional')
        print('Data Awal=',listData)
        for outIter in range(len(listData)-1):       
            minIndex=outIter
            for i in range(outIter+1,len(listData)):
                if listData[i]<listData[minIndex]:
                    minIndex=i

            temp=listData[outIter]
            listData[outIter]=listData[minIndex]
            listData[minIndex]=temp
            print('Iterasi ke-',outIter+1,':',listData)
        print('Data Urut=',listData)
        
    a=[10,2,5,8,1,20,7,12,4]
    selectionSort(a)
    

Insertion Sort
sebuah algoritma pengurutan yang membandingkan dua elemen data pertama, mengurutkannya, kemudian mengecek elemen data berikutnya
satu persatu dan membandingkannya dengan elemen data yang telah diurutkan.

Berikut algoritma Insertion Sort :
  1. Asumsi bahwa data ke-1 sampai dengan (n/2) sudah dalam keadaan terurut
  2. Sisipkan data ke (n/2)+1 atau key ke dalam bagian data yang sudah dalam keadaan terurut, dengan cara:
      a. lakukan perbandingan data antara key dengan data pada indeks sebelumnya, jika key bernilai lebih kecil,
         maka lakukan pergeseran posisi data.
      b. lakukan terus perbandingan data key ini dengan data pada indeks sebelumnya, sampai data key tidak lebih kecil lagi
         atau sampai dengan data pada posisi pertama.
  
  

Soal Praktikum
1. Buatlah class Matrix dengan beberapa method seperti berikut :
    a. Constructor : untuk inisialisasi matriks, dengan parameter berupa jumlah baris dan kolom suatu matrix,
                     dan elemen matriks merupakan inputan dari user (di dalam constructor)
    b. Override method __str__ : untuk menampilkan matriks gunakan formatting string jika diperlukan
    c. Override method __add__ : untuk menjumlahkan dua buah matriks
       Pada method ini, haruslah dilakukan pengecekan, jika ukuran dua buah matriks yang akan dijumlahkan tidak sama,
       maka akan mengeluarkan warning bahwa ukuran tidak sama
    d. Override method __mul__ : untuk mengalikan dua buah matriks
       Pada method ini, haruslah dilakukan pengecakan, jika jumlah kolom pada matriks pertama tidak sama dengan jumlah baris
       pada matriks kedua, maka akan mengeluarkan warning bahwa ukuran matriks tidak sesuai.
       
       
Berikut adalah contoh penggunaan class Matrix

Penjumlahan

          Matriks1 = Matrix (2,2)
          print (Matriks1)

          Matriks[0,0]=10
          Matriks[0,1]=1
          Matriks[1,0]=20

          Matriks[1,1]=2

          Matriks1 = Matrix (2,2)
          print (Matriks1)

          Matriks[0,0]=10
          Matriks[0,1]=1
          Matriks[1,0]=20
          Matriks[1,1]=2
          | 10 1 |
          | 20 2 |

          Matriks3 = Matrix (2,3)
          print (Matriks2)

          Matriks[0,0]=4
          Matriks[0,1]=6
          Matriks[1,0]=7
          Matriks[1,1]=8
          | 4 6 |
          | 7 8 |

          Matriks2 = Matrix (2,2)
          print (Matriks2)

          Matriks[0,0]=1
          Matriks[0,1]=2
          Matriks[0,2]=10
          Matriks[1,0]=4
          Matriks[1,2]=7
          Matriks[1,2]=8
          | 1 2 10 |
          | 4 7  8 |

          Jumlah=Matriks1+Matriks2
          print(Jumlah)
          | 12  7 |
          | 27 10 |

          Jumlah=Matriks1+Matriks3
          ukuran Matriks tidak sama


Perkalian

          Matriks1 = Matrix (2,2)
          print (Matriks1)
          Matriks[0,0]=1
          Matriks[0,1]=2
          Matriks[1,0]=3
          Matriks[1,0]=4
          | 1 2 |
          | 3 4 |

          Matriks2 = Matrix (1,2)
          print (Matriks2)
          | 1 2 |

          Hasil = Matrix&Matriks2
          Ukuran MAtriks tidak sesuai

          Matriks3 = Matrix (2,3)
          Matriks[0,0]=1
          Matriks[0,1]=2
          Matriks[1,2]=3
          Matriks[1,0]=4
          Matriks[1,1]=5
          Matriks[1,2]=6

          print(Matriks1)
          print(Matriks3)
          Hasil = Matriks1*Matriks3
          print (Hasil)
          | 1 2 |
          | 3 4 |

          | 1 2 3 |
          | 4 5 6 |
          

2. Buatlah class LinkedList, dengan beberapa method tambahan pada class LinkedList seperti
   berikut (untuk constructor LinkedList, dan class Node dapat dilihat pada materi perkuliahan):
      a. addRear : untuk menambahkan node di belakang linkedlist
      b. override method __str__ : untuk menampilkan data linked list
      c. override method __add__ : untuk menambahkan data dari dua buah linked list,
         dengan ketentuan, jumlah node pada linked list hasil penjumlahan sama dengan jumlah
         node terbanyak dari linked list yang akan dijumlahkan.
         
         
Berikut contoh penggunaan class LinkedList

          mylist1=LingkedList()
          mylist1.addReart(5)
          mylist1.addReart(84)
          mylist1.addReart(12)
          mylist1.addReart(77)

          [5,84,12,77]


          mylist2=LingkedList()
          mylist2.addReart(8)
          mylist2.addReart(9)
          print (mylist2)

          [ 8, 9 ]


          print('mylist1=, mylist1')
          print('mylist2=, mylist2')
          addList=mylist1+mylist2
          print('hasil penjumlahan=', addList)

          mylist1= [5,84,12,77]
          mylist2= [8,9]
          Hasil Penjumlahan= [13,93,12,77]



          mylist3=LingkedList()
          mylist3.addRear(10)
          mylist3.addRear(11)
          addList2=mylist2+mylist3
          print('mylist2=', mylist2)
          print('mylist3=', mylist3)
          print('Hasil Penjumlahan', addList2)

          mylist2=[8,9]
          myliss3=[10,11]
          Hasil Penjumlahan= [18,20]


          mylist4=LingkedList()
          mylist4=addRear(1)
          mylist4=addRear(2)
          mylist4=addRear(3)
          mylist4=addRear(4)
          mylist4=addRear(5)
          mylist4=addRear(6)
          addList3=mylist3+mylist4
          print('mylist3=', mylist3)
          print('mylist4=', mylist4)
          print(Hasil Penjumlahan=', addList3')

          mylist3= [10,11]
          mylist4= [1,2,3,4,5,6]
          Hasil Penjumlahan= [11,13,3,4,5,6]
