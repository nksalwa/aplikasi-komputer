
# EMT untuk Perhitungan Aljabar

Pada notebook ini Anda belajar menggunakan EMT untuk melakukan
berbagai perhitungan terkait dengan materi atau topik dalam Aljabar.
Kegiatan yang harus Anda lakukan adalah sebagai berikut:


* 
Membaca secara cermat dan teliti notebook ini;

* 
Menerjemahkan teks bahasa Inggris ke bahasa Indonesia;

* 
Mencoba contoh-contoh perhitungan (perintah EMT) dengan cara
* meng-ENTER setiap perintah EMT yang ada (pindahkan kursor ke baris
* perintah)

* 
Jika perlu Anda dapat memodifikasi perintah yang ada dan memberikan
* keterangan/penjelasan tambahan terkait hasilnya.

* 
Menyisipkan baris-baris perintah baru untuk mengerjakan soal-soal
* Aljabar dari file PDF yang saya berikan;

* 
Memberi catatan hasilnya.

* 
Jika perlu tuliskan soalnya pada teks notebook (menggunakan format
* LaTeX).

* 
Gunakan tampilan hasil semua perhitungan yang eksak atau simbolik
* dengan format LaTeX. (Seperti contoh-contoh pada notebook ini.)


## Contoh pertama

Menyederhanakan bentuk aljabar:


$$6x^{-3}y^5\times -7x^2y^{-9}$$\>$&6\*x^(-3)\*y^5\*-7\*x^2\*y^(-9)


$$-\frac{42}{x\,y^4}$$Menjabarkan:


$$(6x^{-3}+y^5)(-7x^2-y^{-9})$$\>$&showev('expand((6\*x^(-3)+y^5)\*(-7\*x^2-y^(-9))))


$${\it expand}\left(\left(-\frac{1}{y^9}-7\,x^2\right)\,\left(y^5+  \frac{6}{x^3}\right)\right)=-7\,x^2\,y^5-\frac{1}{y^4}-\frac{6}{x^3  \,y^9}-\frac{42}{x}$$## Contoh lainnya

$$(\frac {24a^{10}b^{-8}c^7}{12a^6b^{-3}c^5})^{-5}$$\>$&((24\*a^(10)\*b^(-8)\*c^(7))/(12\*a^6\*b^(-3)\*c^5))^-5


$$\frac{b^{25}}{32\,a^{20}\,c^{10}}$$$$(\frac{125p^{12}q^{-14}r^{22}}{25p^8q^6r^{-15}})^{-4}$$\>$&((125\*p^(12)\*q^(-14)\*r^(22))/(25\*p^6\*q^(6)\*r^(-15)))^-4


$$\frac{q^{80}}{625\,p^{24}\,r^{148}}$$$$(m^{x-b}\times n^{x+b})^x(m^bn^{-b})^x$$\>$&(m^(x-b)\*n^(x+b))^x\*(m^b\*n^(-b))^x


$$\left(\frac{m^{b}}{n^{b}}\right)^{x}\,\left(m^{x-b}\,n^{x+b}\right)  ^{x}$$$$(-5m^4n^2)(6m^2n^3)$$\>$&(-5\*m^4\*n^2)\*(6\*m^2\*n^3)


$$-30\,m^6\,n^5$$$$(8y^5)(9y)$$\>$&(8\*y^5)\*(9\*y)


$$72\,y^6$$## Baris Perintah

Baris perintah Euler terdiri dari satu atau beberapa perintah Euler
diikuti dengan titik koma ";" atau koma ",". Titik koma mencegah
pencetakan hasilnya. Koma setelah perintah terakhir dapat dihilangkan.


Baris perintah berikut hanya akan mencetak hasil ekspresi, bukan tugas
atau perintah format.


\>r:=2; h:=4; pi\*r^2\*h/3


    16.7551608191

Perintah harus dipisahkan dengan bagian kosong. Baris perintah berikut
mencetak dua hasil.


\>pi\*2\*r\*h, %+2\*pi\*r\*h // Ingat tanda % menyatakan hasil perhitungan terakhir sebelumnya


    50.2654824574
    100.530964915

Baris perintah dijalankan sesuai urutan yang ditekan kembali oleh
pengguna. Jadi, Anda mendapatkan nilai baru setiap kali Anda
menjalankan baris yang kedua.


\>x := 1;

\>x := cos(x) // nilai cosinus (x dalam radian)


    0.540302305868

\>x := cos(x)


    0.857553215846

Jika dua baris dihubungkan dengan "..." kedua baris akan selalu
dijalankan secara bersamaan.


\>x := 1.5; ...  
\>   x := (x+2/x)/2, x := (x+2/x)/2, x := (x+2/x)/2, 


    1.41666666667
    1.41421568627
    1.41421356237

Ini juga merupakan cara yang baik untuk menyebarkan perintah panjang
ke dua baris atau lebih. Anda dapat menekan Ctrl+Return untuk membagi
baris menjadi dua pada posisi kursor saat ini, atau Ctrl+Back untuk
menggabungkan baris.


Untuk melipat semua multi-garis tekan Ctrl+L. Maka baris-baris
berikutnya hanya akan terlihat, jika salah satunya mendapat fokus.
Untuk melipat satu multi-baris, mulailah baris pertama dengan "%+".


\>%+ x=4+5; ...  
\>    // Garis ini tidak akan terlihat setelah kursor keluar dari garis


Baris yang dimulai dengan %% tidak akan terlihat sama sekali.


    81

Euler mendukung loop (pengulangan) di baris perintah, asalkan cocok ke
dalam satu baris atau multi-baris. Tentu saja, pembatasan ini tidak
berlaku dalam program. Untuk informasi lebih lanjut lihat pendahuluan
berikut.


\>x=1; for i=1 to 5; x := (x+2/x)/2, end; // menghitung akar 2


    1.5
    1.41666666667
    1.41421568627
    1.41421356237
    1.41421356237

Tidak apa-apa menggunakan multi-baris. Pastikan baris diakhiri dengan
"...".


\>x := 1.5; // komentar buka di sini sebelum ...  
\>   repeat xnew:=(x+2/x)/2; until xnew~=x; ...  
\>      x := xnew; ...  
\>   end; ...  
\>   x,


    1.41421356237

Struktur bersyarat juga berfungsi.


\>if E^pi\>pi^E; then "Thought so!", endif;


    Thought so!

Saat Anda menjalankan perintah, kursor dapat berada di posisi mana pun
di baris perintah. Anda dapat kembali ke perintah sebelumnya atau
melompat ke perintah berikutnya dengan tombol panah. Atau Anda dapat
mengklik bagian komentar di atas perintah untuk membuka perintah.


Saat Anda menggerakkan kursor di sepanjang baris, pasangan tanda
kurung atau tanda kurung buka dan tutup akan disorot. Juga, perhatikan
baris status. Setelah tanda kurung buka dari fungsi sqrt(), baris
status akan menampilkan teks bantuan untuk fungsi tersebut. Jalankan
perintah dengan kunci kembali.


\>sqrt(sin(10°)/cos(20°))


    0.429875017772

Untuk melihat bantuan untuk perintah terbaru, buka jendela bantuan
dengan F1. Di sana, Anda dapat memasukkan teks untuk dicari. Pada
baris kosong, bantuan untuk jendela bantuan akan ditampilkan. Anda
dapat menekan escape untuk menghapus baris, atau untuk menutup jendela
bantuan.


Anda dapat mengklik dua kali pada perintah apa pun untuk membuka
bantuan untuk perintah ini. Coba klik dua kali perintah exp di bawah
ini pada baris perintah.


\>exp(log(2.5))


    2.5

Anda juga dapat menyalin (copy) dan menempel (paste) di Euler. Gunakan
Ctrl+C dan Ctrl+V untuk ini. Untuk menandai teks, seret mouse atau
gunakan shift bersamaan dengan tombol kursor apa pun. Selain itu, Anda
dapat menyalin tanda kurung yang disorot.


## Contoh lainnya

$$cos(45) $$\>cos(45°)


    0.707106781187

$$tan (85.4)$$\>tan(85.4°)


    12.4288310198

$$\frac {pi}{4}$$\>pi/4


    0.785398163397

$$\frac{3pi}{2}$$\>3\*pi/2


    4.71238898038

$$8pi=...radian$$\>pi=22/7;

\>8\*pi


    25.1428571429

## Sintaks Dasar

Euler mengetahui fungsi matematika yang biasa digunakan. Seperti yang
Anda lihat di atas, fungsi trigonometri bekerja dalam radian atau
derajat. Untuk mengonversi ke derajat, tambahkan simbol derajat
(dengan tombol F7) ke nilainya, atau gunakan fungsi rad(x). Fungsi
akar kuadrat disebut sqrt di Euler. Tentu saja, bisa juga menggunakan
x^(1/2).


Untuk menyetel variabel, gunakan "=" atau ":=". Demi kejelasan,
pendahuluan ini menggunakan bentuk yang terakhir. Spasi tidak penting.
Tapi diharapkan ada jarak antar perintah.


Beberapa perintah dalam satu baris dipisahkan dengan "," atau ";".
Titik koma menekan keluaran perintah. Di akhir baris perintah, ","
diasumsikan, jika ";" hilang.


\>g:=9.81; t:=2.5; 1/2\*g\*t^2


    30.65625

EMT menggunakan sintaks pemrograman untuk ekspresi. Untuk memasukkan


$$e^2 \cdot \left( \frac{1}{3+4 \log(0.6)}+\frac{1}{7} \right)$$Anda harus mengatur tanda kurung yang benar dan menggunakan / untuk
pecahan. Perhatikan tanda kurung yang disorot untuk mendapatkan
bantuan. Perhatikan bahwa konstanta Euler e diberi nama E dalam EMT.


\>E^2\*(1/(3+4\*log(0.6))+1/7)


    8.77908249441

Untuk menghitung ekspresi rumit seperti


$$\left(\frac{\frac17 + \frac18 + 2}{\frac13 + \frac12}\right)^2 \pi$$Anda harus memasukkannya dalam form baris.


\>((1/7 + 1/8 + 2) / (1/3 + 1/2))^2 \* pi


    23.2671801626

Letakkan tanda kurung dengan hati-hati di sekitar sub-ekspresi yang
perlu dihitung terlebih dahulu. EMT membantu Anda dengan menyorot
ekspresi yang mengakhiri tanda kurung tutup. Anda juga harus
memasukkan nama "pi" untuk huruf Yunani pi.


Hasil perhitungan ini berupa bilangan floating point. Ini secara
default dicetak dengan akurasi sekitar 12 digit. Di baris perintah
berikut, kita juga mempelajari bagaimana kita bisa merujuk ke hasil
sebelumnya dalam baris yang sama.


\>1/3+1/7, fraction %


    0.47619047619
    10/21

Perintah Euler dapat berupa ekspresi atau perintah biasa. Ekspresi
terbuat dari operator dan fungsi. Jika perlu, harus berisi tanda
kurung untuk memastikan urutan eksekusi yang benar. Jika ragu,
memasang tanda kurung adalah ide yang bagus. Perhatikan bahwa EMT
menampilkan tanda kurung buka dan tutup saat mengedit baris perintah.


\>(cos(pi/4)+1)^3\*(sin(pi/4)+1)^2


    14.4978445072

Operator numerik Euler meliputi:


 + unary atau operator plus  
 - unary atau operator minus  
 *, /  
 . produk matriks  
 a^b pangkat untuk a positif atau bilangan bulat b (bisa juga a**b)  
 n! operator faktorial  

dan masih banyak lagi.


Berikut beberapa fungsi yang mungkin Anda perlukan. Masih banyak lagi.


 sin,cos,tan,atan,asin,acos,rad,deg  
 log,exp,log10,sqrt,logbase  
 bin,logbin,logfac,mod,floor,ceil,round,abs,sign  
 conj,re,im,arg,conj,real,complex  
 beta,betai,gamma,complexgamma,ellrf,ellf,ellrd,elle  
 bitand,bitor,bitxor,bitnot  

Beberapa perintah memiliki alias, misalnya ln untuk log.


\>ln(E^2), arctan(tan(0.5))


    2
    0.5

\>sin(30°)


    0.5

Pastikan untuk menggunakan tanda kurung (tanda kurung bulat), setiap
kali ada keraguan tentang urutan eksekusi! Berikut ini tidak sama
dengan (2^3)^4, yang merupakan default untuk 2^3^4 di EMT (beberapa
sistem numerik melakukannya dengan cara lain).


\>2^3^4, (2^3)^4, 2^(3^4)


    2.41785163923e+24
    4096
    2.41785163923e+24

## Contoh lainnya

$$7(3x+6)=11-(x+2)$$\>$& 7\*(3\*x+6)=11-(x+2)


$$7\,\left(3\,x+6\right)=9-x$$$$(-5m^4n^2)(6m^2n^3)$$\>$& (-5\*m^4\*n^2)\*(6\*m^2\*n^3)


$$-30\,m^6\,n^5$$Menunjukkan pentingnya penggunaan tanda kurung pada EMT


$$(y-2)(y+2)(y^2+4)$$\>$&(y-2)\*(y+2)\*(y^2+4) 


$$\left(y-2\right)\,\left(y+2\right)\,\left(y^2+4\right)$$$$y-2*y+2*y^2+4$$\>$& y-2\*y+2\*y^2+4


$$2\,y^2-y+4$$$$sin(37)cos(22)+cos(37)sin(22)$$\>sin (37°)\*cos (22°)+ cos (37°) \*sin (22°)


    0.857167300702

## Bilangan Real

Tipe data primer pada Euler adalah bilangan real. Real
direpresentasikan dalam format IEEE dengan akurasi sekitar 16 digit
desimal.


\>longest 1/3


         0.3333333333333333 

Representasi ganda internal membutuhkan 8 byte.


\>printdual(1/3)


    1.0101010101010101010101010101010101010101010101010101*2^-2

\>printhex(1/3)


    5.5555555555554*16^-1

## Contoh lainnya

$$\sqrt{\frac{3}{7}}$$\>longest sqrt(3/7)


         0.6546536707079771 

\>printdual (sqrt(3/7))


    1.0100111100101110110001000001001111001011010100101010*2^-1

\>printhex (sqrt(3/7))


    A.7976209E5A950*16^-1

$$\sqrt[3]{\frac{3}{5}}$$\>longest (3/5)^(1/3)


         0.8434326653017492 

\>printdual ((3/5)^(1/3))


    1.1010111111010110011010000000001110110010110000001100*2^-1

## Strings

Sebuah string di Euler didefinisikan dengan "...".


\>"A string can contain anything."


    A string can contain anything.

String dapat digabungkan dengan | atau dengan +. Ini juga berfungsi
dengan angka, yang dalam hal ini diubah menjadi string.


\>"The area of the circle with radius " + 2 + " cm is " + pi\*4 + " cm^2."


    The area of the circle with radius 2 cm is 12.5663706144 cm^2.

Fungsi print juga mengubah angka menjadi string. Ini dapat memerlukan
sejumlah digit dan sejumlah tempat (0 untuk keluaran padat), dan
optimalnya satuan.


\>"Golden Ratio : " + print((1+sqrt(5))/2,5,0)


    Golden Ratio : 1.61803

Ada string khusus bernama none yang tidak dicetak. Itu dikembalikan
oleh beberapa fungsi, ketika hasilnya tidak menjadi masalah. (Ini
dikembalikan secara otomatis, jika fungsi tidak memiliki pernyataan
return.)


\>none


Untuk mengonversi string menjadi angka, cukup evaluasi saja. Ini juga
berfungsi untuk ekspresi (lihat di bawah).


\>"1234.5"()


    1234.5

Untuk mendefinisikan vektor string, gunakan notasi vektor [...].


\>v:=["affe","charlie","bravo"]


    affe
    charlie
    bravo

Vektor string kosong dilambangkan dengan [none]. Vektor string dapat
digabungkan.


\>w:=[none]; w|v|v


    affe
    charlie
    bravo
    affe
    charlie
    bravo

String dapat berisi karakter Unicode. Secara internal, string ini
berisi kode UTF-8. Untuk menghasilkan string seperti itu, gunakan
u"..." dan salah satu entitas HTML.


String Unicode dapat digabungkan seperti string lainnya.


\>u"&alpha; = " + 45 + u"&deg;" // pdfLaTeX mungkin gagal menampilkan secara benar


    α = 45°

I


Di komentar, entitas yang sama seperti α, β dll. dapat
digunakan. Ini mungkin merupakan alternatif cepat untuk Latex. (Detail
lebih lanjut di komentar di bawah).


Ada beberapa fungsi untuk membuat atau menganalisis string unicode.
Fungsi strtochar() akan mengenali string Unicode, dan menerjemahkannya
dengan benar.


\>v=strtochar(u"&Auml; is a German letter")


    [196,  32,  105,  115,  32,  97,  32,  71,  101,  114,  109,  97,  110,
    32,  108,  101,  116,  116,  101,  114]

Hasilnya adalah vektor angka Unicode. Fungsi kebalikannya adalah
chartoutf().


\>v[1]=strtochar(u"&Uuml;")[1]; chartoutf(v)


    Ü is a German letter

Fungsi utf() dapat menerjemahkan string dengan entitas dalam variabel
menjadi string Unicode.


\>s="We have &alpha;=&beta;."; utf(s) // pdfLaTeX mungkin gagal menampilkan secara benar


    We have α=β.

Dimungkinkan juga untuk menggunakan entitas numerik.


\>u"&#196;hnliches"


    Ähnliches

## Contoh lainnya

\>"Find the domain of the rational expression."


    Find the domain of the rational expression.

\>s=strtochar("Simplify")


    [83,  105,  109,  112,  108,  105,  102,  121]

\>"sin"+ u"&theta; =" +" 24/5"


    sinθ = 24/5

\>"cos"+45+u"&deg;"


    cos45°

\>"Given that cos" + u"&theta;=" + 0.9651+ ", find csc (" + 90 + u"&deg;" + "-" + u"&theta;" + ")"  


    Given that cosθ=0.9651, find csc (90°-θ)

## Nilai Boolean

Nilai Boolean diwakili dengan 1=true atau 0=false di Euler. String
dapat dibandingkan, seperti halnya angka.


\>2<1, "apel"<"banana"


    0
    1

"dan" adalah operator "&amp;&amp;" dan "atau" adalah operator "||", seperti
dalam bahasa C. (Kata "dan" dan "atau" hanya dapat digunakan dalam
kondisi "if".)


\>2<E && E<3


    1

Operator Boolean mematuhi aturan bahasa matriks.


\>(1:10)\>5, nonzeros(%)


    [0,  0,  0,  0,  0,  1,  1,  1,  1,  1]
    [6,  7,  8,  9,  10]

Anda dapat menggunakan fungsi nonzeros() untuk mengekstrak elemen
tertentu dari vektor. Dalam contoh ini, kita menggunakan kondisi
isprime(n).


\>N=2|3:2:99 // N berisi elemen 2 dan bilangan2 ganjil dari 3 s.d. 99


    [2,  3,  5,  7,  9,  11,  13,  15,  17,  19,  21,  23,  25,  27,  29,
    31,  33,  35,  37,  39,  41,  43,  45,  47,  49,  51,  53,  55,  57,
    59,  61,  63,  65,  67,  69,  71,  73,  75,  77,  79,  81,  83,  85,
    87,  89,  91,  93,  95,  97,  99]

\>N[nonzeros(isprime(N))] //pilih anggota2 N yang prima


    [2,  3,  5,  7,  11,  13,  17,  19,  23,  29,  31,  37,  41,  43,  47,
    53,  59,  61,  67,  71,  73,  79,  83,  89,  97]

## Contoh lainnya

\>(4:8)\>5


    [0,  0,  1,  1,  1]

\>X=2:2:10


    [2,  4,  6,  8,  10]

\>X[nonzeros(isprime(X))]


    2

\>2<4 && 6<3


    0

\>5<8


    1

## Format Output

Format default output atau keluaran EMT mencetak 12 digit. Untuk
memastikan bahwa kami melihat defaultnya, kami mengatur ulang
formatnya.


\>defformat; pi


    3.14159265359

Secara internal, EMT menggunakan standar IEEE untuk bilangan ganda
dengan sekitar 16 digit desimal. Untuk melihat jumlah digit secara
lengkap gunakan perintah "longestformat", atau kita gunakan operator
"longest" untuk menampilkan hasilnya dalam format terpanjang.


\>longest pi


          3.141592653589793 

Berikut adalah representasi heksadesimal internal dari bilangan ganda.


\>printhex(pi)


    3.243F6A8885A30*16^0

Format output dapat diubah secara permanen dengan perintah format.


\>format(12,5); 1/3, pi, sin(1)


        0.33333 
        3.14159 
        0.84147 

Defaultnya adalah format(12).


\>format(12); 1/3


    0.333333333333

Fungsi seperti "shortestformat", "shortformat", "longformat" berfungsi
untuk vektor dengan cara berikut.


\>shortestformat; random(3,8)


      0.66    0.2   0.89   0.28   0.53   0.31   0.44    0.3 
      0.28   0.88   0.27    0.7   0.22   0.45   0.31   0.91 
      0.19   0.46  0.095    0.6   0.43   0.73   0.47   0.32 

Format default untuk skalar adalah format(12). Tapi ini bisa diubah.


\>setscalarformat(5); pi


    3.1416

Fungsi "longestformat" juga mengatur format skalar.


\>longestformat; pi


    3.141592653589793

Sebagai referensi, berikut adalah daftar format output terpenting.


 shortestformat shortformat longformat, longestformat  
 format(length,digits) goodformat(length)  
 fracformat(length)  
 defformat  

Akurasi internal EMT adalah sekitar 16 desimal, yang merupakan standar
IEEE. Nomor disimpan dalam format internal ini.


Namun format keluaran EMT dapat diatur dengan cara yang fleksibel.


\>longestformat; pi,


    3.141592653589793

\>format(10,5); pi


      3.14159 

Defaultnya adalah defformat().


\>defformat; // default


Ada operator pendek yang hanya mencetak satu nilai. Operator "longest"
akan mencetak semua digit nomor yang valid.


\>longest pi^2/2


          4.934802200544679 

Ada juga operator singkat untuk mencetak hasil dalam format pecahan.
Kami sudah menggunakannya di atas.


\>fraction 1+1/2+1/3+1/4


    25/12

Karena format internal menggunakan cara biner untuk menyimpan angka,
nilai 0,1 tidak akan direpresentasikan secara tepat. Kesalahannya
bertambah sedikit, seperti yang Anda lihat pada perhitungan berikut.


\>longest 0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1-1


     -1.110223024625157e-16 

Tetapi dengan "longformat" default Anda tidak akan menyadarinya. Untuk
kenyamanan, keluaran angka yang sangat kecil adalah 0.


\>0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1-1


    0

# Contoh lainnya

\>fraction 34/65+78/34


    3113/1105

\>longest 3113/1105


          2.817194570135747 

\>shortest 3113/1105


       2.8 

\>format(10,5); 3113/1105


      2.81719 

\>printhex(3113/1105)


    2.D133A9D133A9E*16^0

# Ekspresi

String atau nama dapat digunakan untuk menyimpan ekspresi matematika,
yang dapat dievaluasi dengan EMT. Untuk ini, gunakan tanda kurung
setelah ekspresi. Jika Anda ingin menggunakan string sebagai ekspresi,
gunakan konvensi untuk menamainya "fx" atau "fxy" dll. Ekspresi lebih
diutamakan daripada fungsi.


Variabel global dapat digunakan dalam evaluasi.


\>r:=2; fx:="pi\*r^2"; longest fx()


          12.56637061435917 

Parameter ditetapkan ke x, y, dan z dalam urutan itu. Parameter
tambahan dapat ditambahkan menggunakan parameter yang ditetapkan.


\>fx:="a\*sin(x)^2"; fx(5,a=-1)


    -0.919535764538

Perhatikan bahwa ekspresi akan selalu menggunakan variabel global,
meskipun ada variabel dalam fungsi dengan nama yang sama. (Jika tidak,
evaluasi ekspresi dalam fungsi dapat memberikan hasil yang sangat
membingungkan bagi pengguna yang memanggil fungsi tersebut.)


\>at:=4; function f(expr,x,at) := expr(x); ...  
\>   f("at\*x^2",3,5) // computes 4\*3^2 not 5\*3^2


    36

Jika Anda ingin menggunakan nilai lain untuk "at" selain nilai global,
Anda perlu menambahkan "at=value".


\>at:=4; function f(expr,x,a) := expr(x,at=a); ...  
\>   f("at\*x^2",3,5)


    45

Sebagai referensi, kami mencatat bahwa koleksi panggilan (dibahas di
tempat lain) dapat berisi ekspresi. Jadi kita bisa membuat contoh di
atas sebagai berikut.


\>at:=4; function f(expr,x) := expr(x); ...  
\>   f({{"at\*x^2",at=5}},3)


    45

Ekspresi dalam x sering digunakan seperti halnya fungsi.


Perhatikan bahwa mendefinisikan fungsi dengan nama yang sama seperti
ekspresi simbolik global akan menghapus variabel ini untuk menghindari
kebingungan antara ekspresi simbolik dan fungsi.


\>f &= 5\*x;

\>function f(x) := 6\*x;

\>f(2)


    12

Berdasarkan konvensi, ekspresi simbolik atau numerik harus diberi nama
fx, fxy, dll. Skema penamaan ini tidak boleh digunakan untuk fungsi.


\>fx &= diff(x^x,x); $&fx


Bentuk ekspresi khusus memungkinkan variabel apa pun sebagai parameter
yang tidak disebutkan namanya untuk mengevaluasi ekspresi, bukan hanya
"x", "y", dll. Untuk ini, mulailah ekspresi dengan "@(variabel) ...".


\>"@(a,b) a^2+b^2", %(4,5)


    @(a,b) a^2+b^2
    41

Hal ini memungkinkan untuk memanipulasi ekspresi dalam variabel lain
untuk fungsi EMT yang memerlukan ekspresi dalam "x".


Cara paling dasar untuk mendefinisikan suatu fungsi sederhana adalah
dengan menyimpan rumusnya dalam ekspresi simbolik atau numerik. Jika
variabel utamanya adalah x, ekspresi dapat dievaluasi seperti halnya
fungsi.


Seperti yang Anda lihat pada contoh berikut, variabel global terlihat
selama evaluasi.


\>fx &= x^3-a\*x;  ...  
\>   a=1.2; fx(0.5)


    -0.475

Semua variabel lain dalam ekspresi dapat ditentukan dalam evaluasi
menggunakan parameter yang ditetapkan.


\>fx(0.5,a=1.1)


Sebuah ekspresi tidak perlu bersifat simbolis. Hal ini diperlukan,
jika ekspresi berisi fungsi, yang hanya diketahui di kernel numerik,
bukan di Maxima.


# Contoh lainnya

\>r:=14; h:=7; fx:="pi\*r^2\*h"; longest fx() //mencari volume tabung


          4310.265120725196 

\>at:=2; function f(expr,x,a) := expr(x,at=a); ...  
\>   f("at\*x^3",2,3)


     24.00000 

\>fx &= x^2-a\*x;  ...  
\>   a=2; fx(10)


     80.00000 

\>f &= 3\*x;

\>function f(x) := 6\*x;

\>f(5)


     30.00000 

\> "@(a,b) (a^2+b^2)-(a\*b)", %(3,2)  


    @(a,b) (a^2+b^2)-(a*b)
      7.00000 

# Matematika Simbolik

EMT melakukan matematika simbolis dengan bantuan Maxima. Untuk
detailnya, mulailah dengan tutorial berikut, atau telusuri referensi
untuk Maxima. Para ahli di Maxima harus memperhatikan bahwa ada
perbedaan sintaksis antara sintaksis asli Maxima dan sintaksis default
ekspresi simbolik di EMT.


Matematika simbolik diintegrasikan secara mulus ke dalam Euler dengan
&amp;. Ekspresi apa pun yang dimulai dengan &amp; adalah ekspresi simbolis.
Itu dievaluasi dan dicetak oleh Maxima.


Pertama-tama, Maxima memiliki aritmatika "infinite" yang dapat
menangani bilangan yang sangat besar.


\>$&44!


Dengan cara ini, Anda dapat menghitung hasil yang besar dengan tepat.
Mari kita menghitung


$$C(44,10) = \frac{44!}{34! \cdot 10!}$$\>$& 44!/(34!\*10!) // nilai C(44,10)


Tentu saja, Maxima memiliki fungsi yang lebih efisien untuk ini
(seperti halnya bagian numerik EMT).


\>$binomial(44,10) //menghitung C(44,10) menggunakan fungsi binomial()


Untuk mempelajari lebih lanjut tentang fungsi tertentu, klik dua kali
padanya. Misalnya, coba klik dua kali pada "&amp;binomial" di baris
perintah sebelumnya. Ini membuka dokumentasi Maxima yang disediakan
oleh penulis program tersebut.


Anda akan mengetahui bahwa cara berikut juga bisa dilakukan.


$$C(x,3)=\frac{x!}{(x-3)!3!}=\frac{(x-2)(x-1)x}{6}$$\>$binomial(x,3) // C(x,3)


$$\frac{\left(x-2\right)\,\left(x-1\right)\,x}{6}$$Jika Anda ingin mengganti x dengan nilai tertentu, gunakan "with".


\>$&binomial(x,3) with x=10 // substitusi x=10 ke C(x,3)


$$120$$Dengan begitu Anda bisa menggunakan solusi suatu persamaan di
persamaan lain.


Ekspresi simbolik dicetak oleh Maxima dalam bentuk 2D. Alasan untuk
ini adalah bendera simbolis khusus di string.


Seperti yang telah Anda lihat pada contoh sebelumnya dan berikut, jika
Anda telah menginstal LaTeX, Anda dapat mencetak ekspresi simbolik
dengan Latex. Jika tidak, perintah berikut akan mengeluarkan pesan
kesalahan.


Untuk mencetak ekspresi simbolik dengan LaTeX, gunakan $ di depan &amp;
(atau Anda dapat menghilangkan &amp;) sebelum perintah. Jangan jalankan
perintah Maxima dengan $, jika Anda belum menginstal LaTeX.


\>$(3+x)/(x^2+1)


Ekspresi simbolik diurai oleh Euler. Jika Anda memerlukan sintaksis
kompleks dalam satu ekspresi, Anda dapat mengapit ekspresi tersebut di
"...". Menggunakan lebih dari sekedar ekspresi sederhana mungkin saja
dilakukan, namun sangat tidak disarankan.


\>&"v := 5; v^2"


    
                                      25
    

Untuk kelengkapannya, kami mencatat bahwa ekspresi simbolik dapat
digunakan dalam program, namun perlu diapit dalam tanda kutip. Selain
itu, akan jauh lebih efektif untuk memanggil Maxima pada waktu
kompilasi jika memungkinkan.


\>$&expand((1+x)^4), $&factor(diff(%,x)) // diff: turunan, factor: faktor


Sekali lagi, % mengacu pada hasil sebelumnya.


Untuk mempermudah kami menyimpan solusi ke variabel simbolik. Variabel
simbolik didefinisikan dengan "&amp;=".


\>fx &= (x+1)/(x^4+1); $&fx


$$\frac{x+1}{x^4+1}$$Ekspresi simbolik dapat digunakan dalam ekspresi simbolik lainnya.


\>$&factor(diff(fx,x))


$$\frac{-3\,x^4-4\,x^3+1}{\left(x^4+1\right)^2}$$Input langsung dari perintah Maxima juga tersedia. Mulai baris
perintah dengan "::". Sintaks Maxima disesuaikan dengan sintaks EMT
(disebut "mode kompatibilitas").


\>&factor(20!)


    
                             2432902008176640000
    

\>::: factor(10!)


    
                                   8  4  2
                                  2  3  5  7
    

\>:: factor(20!)


    
                            18  8  4  2
                           2   3  5  7  11 13 17 19
    

Jika Anda ahli dalam Maxima, Anda mungkin ingin menggunakan sintaks
asli Maxima. Anda dapat melakukan ini dengan ":::".


\>::: av:g$ av^2;


    
                                       2
                                      g
    

\>fx &= x^3\*exp(x), $fx


    
                                     3  x
                                    x  E
    

Variabel tersebut dapat digunakan dalam ekspresi simbolik lainnya.
Perhatikan, bahwa dalam perintah berikut sisi kanan &amp;= dievaluasi
sebelum ditugaskan ke Fx.


\>&(fx with x=5), $%, &float(%)


    
                                         5
                                    125 E
    
    
                              18551.64488782208
    

\>fx(5)


    18551.6448878

Untuk mengevaluasi ekspresi dengan nilai variabel tertentu, Anda dapat
menggunakan operator "with".


Baris perintah berikut juga menunjukkan bahwa Maxima dapat
mengevaluasi ekspresi secara numerik dengan float().


\>&(fx with x=10)-(fx with x=5), &float(%)


    
                                    10        5
                              1000 E   - 125 E
    
    
                             2.20079141499189e+7
    

\>$factor(diff(fx,x,2))


Untuk mendapatkan kode Latex untuk sebuah ekspresi, Anda dapat
menggunakan perintah tex.


\>tex(fx)


    x^3\,e^{x}

Ekspresi simbolik dapat dievaluasi seperti halnya ekspresi numerik.


\>fx(0.5)


    0.206090158838

Dalam ekspresi simbolis, ini tidak berhasil, karena Maxima tidak
mendukungnya. Sebagai gantinya, gunakan sintaks "with" (bentuk
perintah at(...) yang lebih bagus dari Maxima).


\>$&fx with x=1/2


$${\it fx}$$Penugasannya juga bisa bersifat simbolis.


\> $&fx with x=1+t


$${\it fx}$$Perintah solve menyelesaikan ekspresi simbolik untuk variabel di
Maxima. Hasilnya adalah vektor solusi.


\>$&solve(x^2+x=4,x)


$$\left[ x=\frac{-\sqrt{17}-1}{2} , x=\frac{\sqrt{17}-1}{2} \right] $$Bandingkan dengan perintah numerik "solve" di Euler, yang memerlukan
nilai awal, dan opsional nilai target.


\>solve("x^2+x",1,y=4)


           1.56 

Nilai numerik dari solusi simbolik dapat dihitung dengan evaluasi
hasil simbolik. Euler akan membacakan tugas x= dst. Jika Anda tidak
memerlukan hasil numerik untuk perhitungan lebih lanjut, Anda juga
dapat membiarkan Maxima menemukan nilai numeriknya.


\>sol &= solve(x^2+2\*x=4,x); $&sol, sol(), $&float(sol)


$$\left[ x=-\sqrt{5}-1 , x=\sqrt{5}-1 \right] $$          -3.24        1.24 

$$\left[ x=-3.23606797749979 , x=1.23606797749979 \right] $$Untuk mendapatkan solusi simbolik tertentu, seseorang dapat
menggunakan "with" dan indeks.


\>$&solve(x^2+x=1,x), x2 &= x with %[2]; $&x2


$$\frac{\sqrt{5}-1}{2}$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-045.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-045.png)

Untuk menyelesaikan sistem persamaan, gunakan vektor persamaan.
Hasilnya adalah vektor solusi.


\>sol &= solve([x+y=3,x^2+y^2=5],[x,y]); $&sol, $&x\*y with sol[1]


$$2$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-047.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-047.png)

Ekspresi simbolis dapat memiliki flag, yang menunjukkan perlakuan
khusus di Maxima. Beberapa flag dapat digunakan sebagai perintah juga,
yang lainnya tidak. Flag ditambahkan dengan "|" (bentuk yang lebih
bagus dari "ev(...,flags)")


\>$& diff((x^3-1)/(x+1),x) //turunan bentuk pecahan


$$\frac{3\,x^2}{x+1}-\frac{x^3-1}{\left(x+1\right)^2}$$\>$& diff((x^3-1)/(x+1),x) | ratsimp //menyederhanakan pecahan


$$\frac{2\,x^3+3\,x^2+1}{x^2+2\,x+1}$$\>$&factor(%) 


$$\frac{2\,x^3+3\,x^2+1}{\left(x+1\right)^2}$$# Contoh lainnya

\>$& diff((3\*x^2-12\*x+16),x)


$$6\,x-12$$\>$&factor(%)


$$6\,\left(x-2\right)$$\>$&solve(-x^2+6\*x=8,x), x2 &= x with %[2]; $&x2


$$2$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-054.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-054.png)

\>&factor(8!)


    
                                    40320
    

\>$binomial(8,3) // C(8,3) 


$$56$$# Fungsi

Dalam EMT, fungsi adalah program yang didefinisikan dengan perintah
"function". Ini bisa berupa fungsi satu baris atau fungsi multibaris.


Fungsi satu baris dapat berupa numerik atau simbolik. Fungsi satu
baris numerik didefinisikan oleh ":=".


\>function f(x) := x\*sqrt(x^2+1)


Untuk gambaran umum, kami menampilkan semua kemungkinan definisi untuk
fungsi satu baris. Suatu fungsi dapat dievaluasi sama seperti fungsi
Euler bawaan lainnya.


\>f(2)


    4.472135955

Fungsi ini juga dapat digunakan untuk vektor, mengikuti bahasa matriks
Euler, karena ekspresi yang digunakan dalam fungsi tersebut
divektorkan.


\>f(0:0.1:1)


    [0,  0.100499,  0.203961,  0.313209,  0.430813,  0.559017,  0.699714,
    0.854459,  1.0245,  1.21083,  1.41421]

Fungsi dapat diplot. Daripada ekspresi, kita hanya perlu memberikan
nama fungsinya.


Berbeda dengan ekspresi simbolik atau numerik, nama fungsi harus
diberikan dalam string.


\>solve("f",1,y=1)


    0.786151377757

Secara default, jika Anda perlu menimpa fungsi bawaan, Anda harus
menambahkan kata kunci "overwrite". Menimpa fungsi bawaan berbahaya
dan dapat menyebabkan masalah pada fungsi lain yang bergantung pada
fungsi tersebut.


Anda masih dapat memanggil fungsi bawaan sebagai "_...", jika fungsi
tersebut ada di inti Euler.


\>function overwrite sin (x) := \_sin(x°) // redine sine in degrees

\>sin(45)


    0.707106781187

Sebaiknya kita menghilangkan redefinisi sin ini.


\>forget sin; sin(pi/4)


# Contoh lainnya

\>function f(x) := x^2-6

\>f(3)


      3.00000 

\>f(0:0.1:1)


    Real 1 x 11 matrix
    
     -6.00000  -5.99000  -5.96000  -5.91000  -5.84000  -5.75000     ...

\>solve("f",1,y=3)


      3.00000 

\>function overwrite sin (x) := \_sin(x°) // redine sine in degrees

\>sin(60)


      0.86603 

\>forget sin; sin(pi/3)


      0.86603 

## Parameter Bawaan

Fungsi numerik dapat memiliki parameter bawaan.


\>function f(x,a=1) := a\*x^2


Menghilangkan parameter ini akan menggunakan nilai bawaan.


\>f(4)


    16

Menyetelnya akan menimpa nilai default.


\>f(4,5)


    80

Parameter yang ditetapkan akan menimpanya juga. Ini digunakan oleh
banyak fungsi Euler seperti plot2d, plot3d.


\>f(4,a=1)


    16

Jika suatu variabel bukan parameter, maka harus bersifat global.
Fungsi satu baris dapat melihat variabel global.


\>function f(x) := a\*x^2

\>a=6; f(2)


    24

Namun parameter yang ditetapkan mengesampingkan nilai global.


Jika argumen tidak ada dalam daftar parameter yang telah ditentukan
sebelumnya, argumen tersebut harus dideklarasikan dengan ":="!


\>f(2,a:=5)


    20

Fungsi simbolik didefinisikan dengan "&amp;=". Mereka didefinisikan di
Euler dan Maxima, dan bekerja di kedua dunia. Ekspresi yang
didefinisikan dijalankan melalui Maxima sebelum definisi.


\>function g(x) &= x^3-x\*exp(-x); $&g(x)


Fungsi simbolik dapat digunakan dalam ekspresi simbolik.


\>$&diff(g(x),x), $&% with x=4/3


Mereka juga dapat digunakan dalam ekspresi numerik. Tentu saja, ini
hanya akan berfungsi jika EMT dapat menafsirkan semua yang ada di
dalam fungsi tersebut.


\>g(5+g(1))


    178.635099908

Mereka dapat digunakan untuk mendefinisikan fungsi atau ekspresi
simbolik lainnya.


\>function G(x) &= factor(integrate(g(x),x)); $&G(c) // integrate: mengintegralkan


$$\int {g\left(c\right)}{\;dc}$$\>solve(&g(x),0.5) 


    0.703467422498

Berikut ini juga berfungsi, karena Euler menggunakan ekspresi simbolik
dalam fungsi g, jika tidak menemukan variabel simbolik g, dan jika
terdapat fungsi simbolik g.


\>solve(&g,0.5)


    0.703467422498

\>function P(x,n) &= (2\*x-1)^n; $&P(x,n)


$$\left(2\,x-1\right)^{n}$$\>function Q(x,n) &= (x+2)^n; $&Q(x,n)


$$\left(x+2\right)^{n}$$\>$&P(x,4), $&expand(%)


$$16\,x^4-32\,x^3+24\,x^2-8\,x+1$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-060.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-060.png)

\>P(3,4)


    625

\>$&P(x,4)+ Q(x,3), $&expand(%)


$$P\left(x , 4\right)+Q\left(x , 3\right)$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-062.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-062.png)

\>$&P(x,4)-Q(x,3), $&expand(%), $&factor(%)


$$16\,x^4-33\,x^3+18\,x^2-20\,x-7$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-064.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-064.png)

![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-065.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-065.png)

\>$&P(x,4)\*Q(x,3), $&expand(%), $&factor(%)


$$\left(x+2\right)^3\,\left(2\,x-1\right)^4$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-067.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-067.png)

![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-068.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-068.png)

\>$&P(x,4)/Q(x,1), $&expand(%), $&factor(%)


$$\frac{\left(2\,x-1\right)^4}{x+2}$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-070.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-070.png)

![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-071.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-071.png)

\>function f(x) &= x^3-x; $&f(x)


$$x^3-x$$Dengan &amp;= fungsinya bersifat simbolis, dan dapat digunakan dalam
ekspresi simbolik lainnya.


\>$&integrate(f(x),x)


Dengan := fungsinya adalah numerik. Contoh yang baik adalah integral
tentu


$$f(x) = \int_1^x t^t \, dt,$$yang tidak dapat dievaluasi secara simbolis.


Jika kita mendefinisikan ulang fungsi tersebut dengan kata kunci “map”
maka dapat digunakan untuk vektor x. Secara internal, fungsi ini
dipanggil untuk semua nilai x satu kali, dan hasilnya disimpan dalam
vektor.


\>function map f(x) := integrate("x^x",1,x)

\>f(0:0.5:2)


    [-0.783431,  -0.410816,  0,  0.676863,  2.05045]

Fungsi dapat memiliki nilai default untuk parameter.


\>function mylog (x,base=10) := ln(x)/ln(base);


Sekarang fungsinya bisa dipanggil dengan atau tanpa parameter "base".


\>mylog(100), mylog(2^6.7,2)


    2
    6.7

Selain itu, dimungkinkan untuk menggunakan parameter yang ditetapkan.


\>mylog(E^2,base=E)


    2

Seringkali, kita ingin menggunakan fungsi untuk vektor di satu tempat,
dan untuk elemen individual di tempat lain. Hal ini dimungkinkan
dengan parameter vektor.


\>function f([a,b]) &= a^2+b^2-a\*b+b; $&f(a,b), $&f(x,y)


Fungsi simbolik seperti ini dapat digunakan untuk variabel simbolik.


Namun fungsinya juga dapat digunakan untuk vektor numerik.


\>v=[3,4]; f(v)


    17

Ada juga fungsi yang murni simbolik, yang tidak dapat digunakan secara
numerik.


\>function lapl(expr,x,y) &&= diff(expr,x,2)+diff(expr,y,2)//turunan parsial kedua


    
                     diff(expr, y, 2) + diff(expr, x, 2)
    

\>$&realpart((x+I\*y)^4), $&lapl(%,x,y)


$${\it lapl}\left(y^4-6\,x^2\,y^2+x^4 , x , y\right)$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-075.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-075.png)

Namun tentu saja, mereka dapat digunakan dalam ekspresi simbolik atau
dalam definisi fungsi simbolik.


Untuk meringkas


* 
&amp;= mendefinisikan fungsi simbolik,

* 
:= mendefinisikan fungsi numerik,

* 
&amp;&amp;= mendefinisikan fungsi simbolik murni.


# Contoh lainnya

\>function P(x,n) &= x^5-2=0; $&P(x,n) 


$$x^5-2=0$$\>function mylog (x,base=10) := ln(x)/ln(base);

\>mylog(2^2.8,3)


           1.77 

\>function F(x) &= factor(integrate(f(x),x)); $&F(x)


$$\int {f\left(x\right)}{\;dx}$$\>function f(x) &= x^3-5\*x^2+3\*x; $&f(x)


$$x^3-5\,x^2+3\,x$$\>function f([a,b]) &= a^3+2\*a^2-a\*b+b; $&f(a,b)


$$-a\,b+b+a^3+2\,a^2$$\>d=[2,4]; f(d)


          12.00 

# Memecahkan Ekspresi

Ekspresi dapat diselesaikan secara numerik dan simbolis.


Untuk menyelesaikan ekspresi sederhana dari satu variabel, kita dapat
menggunakan fungsi solve(). Dibutuhkan nilai awal untuk memulai
pencarian. Secara internal, solve() menggunakan metode secant.


\>solve("x^2-2",1)


    1.41421356237

Ini juga berfungsi untuk ekspresi simbolik. Ambil fungsi berikut.


\>$&solve(x^2=2,x)


$$\left[ x=-\sqrt{2} , x=\sqrt{2} \right] $$\>$&solve(x^2-2,x)


$$\left[ x=-\sqrt{2} , x=\sqrt{2} \right] $$\>$&solve(a\*x^2+b\*x+c=0,x)


$$\left[ x=\frac{-\sqrt{b^2-4\,a\,c}-b}{2\,a} , x=\frac{\sqrt{b^2-4\,  a\,c}-b}{2\,a} \right] $$\>$&solve([a\*x+b\*y=c,d\*x+e\*y=f],[x,y]) 


$$\left[ \left[ x=\frac{b\,f-c\,e}{b\,d-a\,e} , y=\frac{c\,d-a\,f}{b  \,d-a\,e} \right]  \right] $$\>px &= 4\*x^8+x^7-x^4-x; $&px 


$$4\,x^8+x^7-x^4-x$$Sekarang kita mencari titik yang polinomialnya adalah 2. Dalam
solve(), nilai target default y=0 dapat diubah dengan variabel yang
ditetapkan.


Kami menggunakan y=2 dan memeriksa dengan mengevaluasi polinomial pada
hasil sebelumnya.


\>solve(px,1,y=2), px(%)


    0.966715594851
    2

Memecahkan ekspresi simbolik dalam bentuk simbolik mengembalikan
daftar solusi. Kami menggunakan pemecah simbolis solve() yang
disediakan oleh Maxima.


\>sol &= solve(x^2-x-1,x); $&sol


Cara termudah untuk mendapatkan nilai numerik adalah dengan
mengevaluasi solusi secara numerik seperti halnya ekspresi.


\>longest sol()


        -0.6180339887498949       1.618033988749895 

Untuk menggunakan solusi secara simbolis dalam ekspresi lain, cara
termudah adalah dengan "with".


\> $&x^2 with sol [1], $&expand(x^2-x-1 with sol[2])


$$6-3\,\sqrt{5}$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-086.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-086.png)

Penyelesaian sistem persamaan secara simbolis dapat dilakukan dengan
vektor persamaan dan solver simbolis solve(). Jawabannya adalah daftar
daftar persamaan.


\>$&solve([x+y=2,x^3+2\*y+x=4],[x,y])


$$\left[ \left[ x=-1 , y=3 \right]  , \left[ x=1 , y=1 \right]  ,   \left[ x=0 , y=2 \right]  \right] $$Fungsi f() dapat melihat variabel global. Namun seringkali kita ingin
menggunakan parameter lokal.


$$a^x-x^a = 0.1$$dengan a=3.


\>function f(x,a) := x^a-a^x;


Salah satu cara untuk meneruskan parameter tambahan ke f() adalah
dengan menggunakan daftar dengan nama fungsi dan parameternya (cara
lainnya adalah parameter titik koma).


\>solve({{"f",3}},2,y=0.1)


           2.54 

Ini juga berfungsi dengan ekspresi. Namun kemudian, elemen daftar
bernama harus digunakan. (Lebih lanjut tentang daftar di tutorial
tentang sintaks EMT).


\>solve({{"x^a-a^x",a=3}},2,y=0.1)


      2.54116 

# Contoh lainnya

\>$&solve(4^x=8,x)


$$\left[ x=\frac{\log 8}{\log 4} \right] $$\>$&solve (x^2-x^4=5, x)


$$\left[ x=-\frac{\sqrt{\sqrt{19}\,i+1}}{\sqrt{2}} , x=\frac{\sqrt{  \sqrt{19}\,i+1}}{\sqrt{2}} , x=-\frac{\sqrt{1-\sqrt{19}\,i}}{\sqrt{2  }} , x=\frac{\sqrt{1-\sqrt{19}\,i}}{\sqrt{2}} \right] $$\>$&solve(x^3-2\*x^2+x-24,x) 


$$\left[ x=\frac{\frac{\sqrt{3}\,i}{2}-\frac{1}{2}}{9\,\left(\frac{2  \,\sqrt{322}}{3}+\frac{323}{27}\right)^{\frac{1}{3}}}+\left(\frac{2  \,\sqrt{322}}{3}+\frac{323}{27}\right)^{\frac{1}{3}}\,\left(-\frac{  \sqrt{3}\,i}{2}-\frac{1}{2}\right)+\frac{2}{3} , x=\left(\frac{2\,  \sqrt{322}}{3}+\frac{323}{27}\right)^{\frac{1}{3}}\,\left(\frac{  \sqrt{3}\,i}{2}-\frac{1}{2}\right)+\frac{-\frac{\sqrt{3}\,i}{2}-  \frac{1}{2}}{9\,\left(\frac{2\,\sqrt{322}}{3}+\frac{323}{27}\right)  ^{\frac{1}{3}}}+\frac{2}{3} , x=\left(\frac{2\,\sqrt{322}}{3}+\frac{  323}{27}\right)^{\frac{1}{3}}+\frac{1}{9\,\left(\frac{2\,\sqrt{322}  }{3}+\frac{323}{27}\right)^{\frac{1}{3}}}+\frac{2}{3} \right] $$\>px &= x^2+5\*x; $&px


$$x^2+5\,x$$\>solve(px,1,y=2), px(%)


      0.37228 
      2.00000 

## Menyelesaikan Pertidaksamaan

Untuk menyelesaikan pertidaksamaan, EMT tidak akan dapat melakukannya,
melainkan dengan bantuan Maxima, artinya secara eksak (simbolik).
Perintah Maxima yang digunakan adalah fourier_elim(), yang harus
dipanggil dengan perintah "load(fourier_elim)" terlebih dahulu.


Eliminasi Fourier adalah analog dari eliminasi Gauss untuk linear
(persamaan atau pertidaksamaan). Panggilan fungsi 'fourier_elim
([eq1,eq2,...],[var1,var2,...])' melakukan eliminasi Fourier dengan 


\>&load(fourier\_elim)


    
           C:/Program Files/Euler x64/maxima/share/maxima/5.35.1/share/fo\
    urier_elim/fourier_elim.lisp
    

\>$&fourier\_elim([x^2 - 1\>0],[x]) // x^2-1 \> 0


$$\left[ 1<x \right] \lor \left[ x<-1 \right] $$\>$&fourier\_elim([x^2 - 1<0],[x]) // x^2-1 < 0


$$\left[ -1<x , x<1 \right] $$\>$&fourier\_elim([x^2 - 1 # 0],[x]) // x^-1 <\> 0


$$\left[ -1<x , x<1 \right] \lor \left[ 1<x \right] \lor \left[ x<-1   \right] $$\>$&fourier\_elim([x # 6],[x])


$$\left[ x<6 \right] \lor \left[ 6<x \right] $$\>$&fourier\_elim([x < 1, x \> 1],[x]) // tidak memiliki penyelesaian


$${\it emptyset}$$\>$&fourier\_elim([minf < x, x < inf],[x]) // solusinya R


$${\it universalset}$$\>$&fourier\_elim([x^3 - 1 \> 0],[x])


$$\left[ 1<x , x^2+x+1>0 \right] \lor \left[ x<1 , -x^2-x-1>0   \right] $$\>$&fourier\_elim([cos(x) < 1/2],[x]) // ??? gagal


$$\left[ 1-2\,\cos x>0 \right] $$\>$&fourier\_elim([y-x < 5, x - y < 7, 10 < y],[x,y]) // sistem pertidaksamaan


$$\left[ y-5<x , x<y+7 , 10<y \right] $$\>$&fourier\_elim([y-x < 5, x - y < 7, 10 < y],[y,x])


$$\left[ {\it max}\left(10 , x-7\right)<y , y<x+5 , 5<x \right] $$\>$&fourier\_elim((x + y < 5) and (x - y \>8),[x,y])


$$\left[ y+8<x , x<5-y , y<-\frac{3}{2} \right] $$\>$&fourier\_elim(((x + y < 5) and x < 1) or  (x - y \>8),[x,y])


$$\left[ y+8<x \right] \lor \left[ x<{\it min}\left(1 , 5-y\right)   \right] $$\>&fourier\_elim([max(x,y) \> 6, x # 8, abs(y-1) \> 12],[x,y])


    
            [6 &lt; x, x &lt; 8, y &lt; - 11] or [8 &lt; x, y &lt; - 11]
     or [x &lt; 8, 13 &lt; y] or [x = y, 13 &lt; y] or [8 &lt; x, x &lt; y, 13 &lt; y]
     or [y &lt; x, 13 &lt; y]
    

\>$&fourier\_elim([(x+6)/(x-9) <= 6],[x])


$$\left[ x=12 \right] \lor \left[ 12<x \right] \lor \left[ x<9   \right] $$# Contoh Lainnya

Menyelesaikan pertidaksamaan


$$x+8 \le 9$$\>$&fourier\_elim([x+8 <9],[x])


$$\left[ x<1 \right] $$$$x+6 \ge 7$$\>$&fourier\_elim([x+6 \>= 7],[x])


$$\left[ x=1 \right] \lor \left[ 1<x \right] $$$$2y - 3 \ge 1-y+5$$\>$&fourier\_elim([2\*y - 3\>= 1-y+5],[y])


$$\left[ y=3 \right] \lor \left[ 3<y \right] $$$$(x-2)(x+5) > x(x-3)$$\>$&fourier\_elim([(x-2)\*(x+5) \>x\*(x-3)],[x])


$$\left[ \frac{5}{3}<x \right] $$$$\frac {2x-1}{3} \ge \frac{5}{6}$$\>$&fourier\_elim([(2\*x-1)/3\>= 5/6],[x])


$$\left[ x=\frac{7}{4} \right] \lor \left[ \frac{7}{4}<x \right] $$# Bahasa Matriks

Dokumentasi inti EMT berisi pembahasan rinci tentang bahasa matriks
Euler.


Vektor dan matriks dimasukkan dengan tanda kurung siku, elemen
dipisahkan dengan koma, baris dipisahkan dengan titik koma.


\>A=[1,2;3,4]


                1             2 
                3             4 

Hasil kali matriks dilambangkan dengan titik.


\>b=[3;4]


                3 
                4 

Transpose matriks adalah matriks baru yang diperoleh dengan cara
menukar elemen-elemen baris menjadi elemen kolom atau sebaliknya.


\>b' // transpose b


    [3,  4]

Invers matriks adalah matriks baru yang merupakan kebalikan dari
matriks asal


\>inv(A) //inverse A


               -2             1 
              1.5          -0.5 

Perkalian matriks sendiri adalah proses mengalikan setiap elemen baris
pada matriks pertama dengan elemen kolom pada matriks kedua


\>A.b //perkalian matriks


               11 
               25 

Perkalian dari matriks dengan invers matriks sendiri itu akan
menghasilkan matriks identitas


\>A.inv(A)


                1             0 
                0             1 

Poin utama dari bahasa matriks adalah semua fungsi dan operator
bekerja elemen demi elemen.


Perkalian matriks dan perpangkatan matriks


\>A.A


                7            10 
               15            22 

\>A^2 //perpangkatan elemen2 A


                1             4 
                9            16 

\>A.A.A


               37            54 
               81           118 

\>power(A,3) //perpangkatan matriks


               37            54 
               81           118 

Pembagian matriks


\>A/A //pembagian elemen-elemen matriks yang seletak


                1             1 
                1             1 

\>A/b //pembagian elemen2 A oleh elemen2 b kolom demi kolom (karena b vektor kolom)


         0.333333      0.666667 
             0.75             1 

Perkalian invers matriks dengan matriks lainnya


\>A\\b // hasilkali invers A dan b, A^(-1)b 


               -2 
              2.5 

\>inv(A).b


               -2 
              2.5 

\>A\\A   //A^(-1)A


                1             0 
                0             1 

\>inv(A).A


                1             0 
                0             1 

\>A\*A //perkalian elemen-elemen matriks seletak


                1             4 
                9            16 

Ini bukan hasil kali matriks, melainkan perkalian elemen demi elemen.
Hal yang sama juga berlaku untuk vektor.


\>b^2 // perpangkatan elemen-elemen matriks/vektor


                9 
               16 

Jika salah satu operan adalah vektor atau skalar, maka operan tersebut
diperluas secara alami.


\>2\*A


                2             4 
                6             8 

Misalnya, jika operan adalah vektor kolom, elemennya diterapkan ke
semua baris A.


\>[1,2]\*A


                1             4 
                3             8 

Jika ini adalah vektor baris, maka diterapkan ke semua kolom A.


\>A\*[2,3]


                2             6 
                6            12 

Kita dapat membayangkan perkalian ini seolah-olah vektor baris v telah
diduplikasi untuk membentuk matriks yang berukuran sama dengan A.


\>dup([1,2],2) // dup: menduplikasi/menggandakan vektor [1,2] sebanyak 2 kali (baris)


                1             2 
                1             2 

\>A\*dup([1,2],2) 


                1             4 
                3             8 

Hal ini juga berlaku untuk dua vektor dimana yang satu adalah vektor
baris dan yang lainnya adalah vektor kolom. Kita menghitung i*j untuk
i,j dari 1 sampai 5. Caranya adalah dengan mengalikan 1:5 dengan
transposenya. Bahasa matriks Euler secara otomatis menghasilkan tabel
nilai.


\>(1:5)\*(1:5)' // hasilkali elemen-elemen vektor baris dan vektor kolom


                1             2             3             4             5 
                2             4             6             8            10 
                3             6             9            12            15 
                4             8            12            16            20 
                5            10            15            20            25 

Sekali lagi, ingatlah bahwa ini bukan produk matriks!


\>(1:5).(1:5)' // hasilkali vektor baris dan vektor kolom


    55

\>sum((1:5)\*(1:5)) // sama hasilnya


    55

Bahkan operator seperti &lt; atau == bekerja dengan cara yang sama.


\>(1:10)<6 // menguji elemen-elemen yang kurang dari 6


    [1,  1,  1,  1,  1,  0,  0,  0,  0,  0]

Misalnya, kita dapat menghitung jumlah elemen yang memenuhi kondisi
tertentu dengan fungsi sum().


\>sum((1:10)<6) // banyak elemen yang kurang dari 6


    5

Euler memiliki operator perbandingan, seperti "==", yang memeriksa
persamaan.


Kita mendapatkan vektor 0 dan 1, dimana 1 berarti benar.


\>t=(1:10)^2; t==25 //menguji elemen2 t yang sama dengan 25 (hanya ada 1)


    [0,  0,  0,  0,  1,  0,  0,  0,  0,  0]

Dari vektor tersebut, "nonzeros" memilih elemen bukan nol.


Dalam hal ini, kita mendapatkan indeks semua elemen lebih besar dari
50.


\>nonzeros(t\>50) //indeks elemen2 t yang lebih besar daripada 50


    [8,  9,  10]

Tentu saja, kita dapat menggunakan vektor indeks ini untuk mendapatkan
nilai yang sesuai dalam t.


\>t[nonzeros(t\>50)] //elemen2 t yang lebih besar daripada 50


    [64,  81,  100]

Sebagai contoh, mari kita cari semua kuadrat bilangan 1 sampai 1000,
yang memenuhi 5 modulo 11 dan 3 modulo 13.


\>t=1:1000; nonzeros(mod(t^2,11)==5 && mod(t^2,13)==3)


    [4,  48,  95,  139,  147,  191,  238,  282,  290,  334,  381,  425,
    433,  477,  524,  568,  576,  620,  667,  711,  719,  763,  810,  854,
    862,  906,  953,  997]

EMT tidak sepenuhnya efektif untuk perhitungan bilangan bulat. Ia
menggunakan floating point presisi ganda secara internal. Namun,
seringkali hal ini sangat berguna.


Kita dapat memeriksa primalitasnya. Mari kita cari tahu, berapa banyak
persegi ditambah 1 yang merupakan bilangan prima.


\>t=1:1000; length(nonzeros(isprime(t^2+1)))


    112

Fungsi nonzeros() hanya berfungsi untuk vektor. Untuk matriks,
menggunakan mnonzeros().


\>seed(2); A=random(3,4)


         0.765761      0.401188      0.406347      0.267829 
          0.13673      0.390567      0.495975      0.952814 
         0.548138      0.006085      0.444255      0.539246 

Ini mengembalikan indeks elemen, yang bukan nol.


\>k=mnonzeros(A<0.4) //indeks elemen2 A yang kurang dari 0,4


                1             4 
                2             1 
                2             2 
                3             2 

Indeks ini dapat digunakan untuk mengatur elemen ke nilai tertentu.


\>mset(A,k,0) //mengganti elemen2 suatu matriks pada indeks tertentu


         0.765761      0.401188      0.406347             0 
                0             0      0.495975      0.952814 
         0.548138             0      0.444255      0.539246 

Fungsi mset() juga dapat mengatur elemen pada indeks ke entri beberapa
matriks lainnya.


\>mset(A,k,-random(size(A)))


         0.765761      0.401188      0.406347     -0.126917 
        -0.122404     -0.691673      0.495975      0.952814 
         0.548138     -0.483902      0.444255      0.539246 

Dan dimungkinkan untuk mendapatkan elemen dalam vektor.


\>mget(A,k)


    [0.267829,  0.13673,  0.390567,  0.006085]

Fungsi lain yang berguna adalah ekstrem, yang mengembalikan nilai
minimal dan maksimal di setiap baris matriks dan posisinya.


\>ex=extrema(A)


         0.267829             4      0.765761             1 
          0.13673             1      0.952814             4 
         0.006085             2      0.548138             1 

Kita dapat menggunakan ini untuk mengekstrak nilai maksimal di setiap
baris.


\>ex[,3]'


    [0.765761,  0.952814,  0.548138]

Ini tentu saja sama dengan fungsi max().


\>max(A)'


    [0.765761,  0.952814,  0.548138]

Namun dengan mget(), kita dapat mengekstrak indeks dan menggunakan
informasi ini untuk mengekstrak elemen pada posisi yang sama dari
matriks lain.


\>j=(1:rows(A))'|ex[,4], mget(-A,j)


# Contoh lainnya

Tentukan nilai-nilai yang diminta pada soal di bawah ini


\>A=[1,2;4,3]


                1             2 
                4             3 

\>B =[-3,5;2,-1]


               -3             5 
                2            -1 

$$A+B$$\>A+B


               -2             7 
                6             2 

$$A-B$$\>A-B


                4            -3 
                2             4 

$$B\times A$$\>B\*A


               -3            10 
                8            -3 

$$2 \times A$$\>2\*A


                2             4 
                8             6 

$$B+A$$\>B+A


               -2             7 
                6             2 

# Fungsi Matriks Lainnya (Building Matriks)

Untuk membangun sebuah matriks, kita dapat menumpuk satu matriks di
atas matriks lainnya. Jika keduanya tidak memiliki jumlah kolom yang
sama, maka kolom yang lebih pendek akan diisi dengan 0.


\>v=1:3; v\_v


                1             2             3 
                1             2             3 

Demikian pula, kita dapat melampirkan matriks ke matriks lain secara
berdampingan, jika keduanya mempunyai jumlah baris yang sama.


\>A=random(3,4); A|v'


         0.655416      0.200995      0.893622      0.281887             1 
            0.525      0.314127      0.444616      0.299474             2 
          0.28269      0.883227      0.270906      0.704419             3 

Jika jumlah barisnya tidak sama, matriks yang lebih pendek diisi
dengan 0.


Ada pengecualian untuk aturan ini. Bilangan real yang melekat pada
suatu matriks akan digunakan sebagai kolom yang diisi dengan bilangan
real tersebut.


\>A|1


         0.655416      0.200995      0.893622      0.281887             1 
            0.525      0.314127      0.444616      0.299474             1 
          0.28269      0.883227      0.270906      0.704419             1 

Dimungkinkan untuk membuat matriks vektor baris dan kolom.


\>[v;v]


                1             2             3 
                1             2             3 

\>[v,v]


    [1,  2,  3,  1,  2,  3]

\>[v',v']


                1             1 
                2             2 
                3             3 

Tujuan utamanya adalah untuk menafsirkan ekspresi vektor untuk vektor
kolom.


\>"[x,x^2]"(v')


                1             1 
                2             4 
                3             9 

Untuk mendapatkan ukuran A, kita bisa menggunakan fungsi berikut.


\>C=zeros(2,4); rows(C), cols(C), size(C), length(C)


    2
    4
    [2,  4]
    4

Untuk vektor, ada length().


\>length(2:10)


    9

Masih banyak fungsi lain yang menghasilkan matriks.


\>ones(2,2)


                1             1 
                1             1 

Ini juga dapat digunakan dengan satu parameter. Untuk mendapatkan
vektor dengan bilangan selain 1, gunakan yang berikut ini.


\>ones(5)\*6


    [6,  6,  6,  6,  6]

Matriks bilangan acak juga dapat dihasilkan dengan acak (distribusi
seragam) atau normal (distribusi Gauß).


\>random(2,2)


          0.66566      0.831835 
            0.977      0.544258 

Berikut adalah fungsi lain yang berguna, yang merestrukturisasi elemen
matriks menjadi matriks lain.


\>redim(1:9,3,3) // menyusun elemen2 1, 2, 3, ..., 9 ke bentuk matriks 3x3


                1             2             3 
                4             5             6 
                7             8             9 

Dengan fungsi berikut, kita dapat menggunakan fungsi ini dan fungsi
dup untuk menulis fungsi rep(), yang mengulangi vektor sebanyak n
kali.


\>function rep(v,n) := redim(dup(v,n),1,n\*cols(v))


Mari kita coba.


\>rep(1:3,5)


    [1,  2,  3,  1,  2,  3,  1,  2,  3,  1,  2,  3,  1,  2,  3]

Fungsi multdup() menduplikasi elemen vektor.


\>multdup(1:3,5), multdup(1:3,[2,3,2])


    [1,  1,  1,  1,  1,  2,  2,  2,  2,  2,  3,  3,  3,  3,  3]
    [1,  1,  2,  2,  2,  3,  3]

Fungsi flipx() dan flipy() mengembalikan urutan baris atau kolom
matriks. Yaitu, fungsi flipx() membalik secara horizontal.


Jika jumlah kolom tidak sama, kolom yang lebih pendek akan diisi 0.


\>flipx(1:5) //membalik elemen2 vektor baris


    [5,  4,  3,  2,  1]

Untuk rotasi, Euler memiliki rotleft() dan rotright().


\>rotleft(1:5) // memutar elemen2 vektor baris


    [2,  3,  4,  5,  1]

Fungsi khusus adalah drop(v,i), yang menghilangkan elemen dengan
indeks di i dari vektor v.


\>drop(10:20,3)


    [10,  11,  13,  14,  15,  16,  17,  18,  19,  20]

Perhatikan bahwa vektor i di drop(v,i) mengacu pada indeks elemen di
v, bukan nilai elemen. Jika Anda ingin menghapus elemen, Anda perlu
mencari elemennya terlebih dahulu. Fungsi indexof(v,x) dapat digunakan
untuk mencari elemen x dalam vektor yang diurutkan v.


\>v=primes(50), i=indexof(v,10:20), drop(v,i)


    [2,  3,  5,  7,  11,  13,  17,  19,  23,  29,  31,  37,  41,  43,  47]
    [0,  5,  0,  6,  0,  0,  0,  7,  0,  8,  0]
    [2,  3,  5,  7,  23,  29,  31,  37,  41,  43,  47]

Seperti yang Anda lihat, tidak ada salahnya memasukkan indeks di luar
rentang (seperti 0), indeks ganda, atau indeks yang tidak diurutkan.


\>drop(1:10,shuffle([0,0,5,5,7,12,12]))


    [1,  2,  3,  4,  6,  8,  9,  10]

Ada beberapa fungsi khusus untuk mengatur diagonal atau menghasilkan
matriks diagonal.


Kita mulai dengan matriks identitas.


\>A=id(5) // matriks identitas 5x5


                1             0             0             0             0 
                0             1             0             0             0 
                0             0             1             0             0 
                0             0             0             1             0 
                0             0             0             0             1 

Kemudian kita atur diagonal bawah (-1) menjadi 1:4.


\>setdiag(A,-1,1:4) //mengganti diagonal di bawah diagonal utama


                1             0             0             0             0 
                1             1             0             0             0 
                0             2             1             0             0 
                0             0             3             1             0 
                0             0             0             4             1 

Perhatikan bahwa kami tidak mengubah matriks A. Kami mendapatkan
matriks baru sebagai hasil dari setdiag().


Berikut adalah fungsi yang mengembalikan matriks tri-diagonal.


\>function tridiag (n,a,b,c) := setdiag(setdiag(b\*id(n),1,c),-1,a); ...  
\>   tridiag(5,1,2,3)


                2             3             0             0             0 
                1             2             3             0             0 
                0             1             2             3             0 
                0             0             1             2             3 
                0             0             0             1             2 

Diagonal suatu matriks juga dapat diekstraksi dari matriks tersebut.
Untuk mendemonstrasikannya, kami menyusun ulang vektor 1:9 menjadi
matriks 3x3.


\>A=redim(1:9,3,3)


                1             2             3 
                4             5             6 
                7             8             9 

Sekarang kita dapat mengekstrak diagonalnya.


\>d=getdiag(A,0)


    [1,  5,  9]

Misalnya. Kita dapat membagi matriks dengan diagonalnya. Bahasa
matriks menjaga agar vektor kolom d diterapkan pada matriks baris demi
baris.


\>fraction A/d'


            1         2         3 
          4/5         1       6/5 
          7/9       8/9         1 

# Contoh lainnya

\>I=id(2)


                1             0 
                0             1 

\>A=redim(1:8,4,2)


                1             2 
                3             4 
                5             6 
                7             8 

\>random(3,3)


         0.655416      0.200995      0.893622 
         0.281887         0.525      0.314127 
         0.444616      0.299474       0.28269 

\>drop(1:20,4)


    [1,  2,  3,  5,  6,  7,  8,  9,  10,  11,  12,  13,  14,  15,  16,  17,
    18,  19,  20]

\> rotleft(5:15)  


    [6,  7,  8,  9,  10,  11,  12,  13,  14,  15,  5]

# Vektorisasi

Hampir semua fungsi di Euler juga berfungsi untuk input matriks dan
vektor, jika hal ini masuk akal.


Misalnya, fungsi sqrt() menghitung akar kuadrat dari semua elemen
vektor atau matriks.


\>sqrt(1:3)


    [1,  1.41421,  1.73205]

Jadi Anda dapat dengan mudah membuat tabel nilai. Ini adalah salah
satu cara untuk memplot suatu fungsi (alternatifnya menggunakan
ekspresi).


\>x=1:0.01:5; y=log(x)/x^2; // terlalu panjang untuk ditampikan


Dengan ini dan operator titik dua a:delta:b, vektor nilai fungsi dapat
dihasilkan dengan mudah.


Pada contoh berikut, kita menghasilkan vektor nilai t[i] dengan jarak
0,1 dari -1 hingga 1. Kemudian kita menghasilkan vektor nilai fungsi


$$s = t^3-t$$\>t=-1:0.1:1; s=t^3-t


    [0,  0.171,  0.288,  0.357,  0.384,  0.375,  0.336,  0.273,  0.192,
    0.099,  0,  -0.099,  -0.192,  -0.273,  -0.336,  -0.375,  -0.384,
    -0.357,  -0.288,  -0.171,  0]

EMT memperluas operator untuk skalar, vektor, dan matriks dengan cara
yang jelas.


Misalnya, vektor kolom dikali vektor baris diekspansi ke matriks, jika
operator diterapkan. Berikut ini, v' adalah vektor yang dialihkan
(vektor kolom).


\>shortest (1:5)\*(1:5)'


         1      2      3      4      5 
         2      4      6      8     10 
         3      6      9     12     15 
         4      8     12     16     20 
         5     10     15     20     25 

Perhatikan, ini sangat berbeda dengan perkalian matriks. Hasil kali
matriks dilambangkan dengan titik "." di EMT.


\>(1:5).(1:5)'


    55

Secara default, vektor baris dicetak dalam format ringkas.


\>[1,2,3,4]


    [1,  2,  3,  4]

Untuk matriks operator khusus . menunjukkan perkalian matriks, dan A'
menunjukkan transposisi. Matriks 1x1 dapat digunakan seperti bilangan
real.


\>v:=[1,2]; v.v', %^2


    5
    25

Untuk mengubah urutan matriks kita menggunakan apostrof.


\>v=1:4; v'


                1 
                2 
                3 
                4 

Jadi kita dapat menghitung matriks A dikalikan vektor b.


\>A=[1,2,3,4;5,6,7,8]; A.v'


               30 
               70 

Perhatikan bahwa v masih merupakan vektor baris. Jadi v'.v berbeda
dengan v.v'.


\>v'.v


                1             2             3             4 
                2             4             6             8 
                3             6             9            12 
                4             8            12            16 

v.v' menghitung norma v kuadrat untuk vektor baris v. Hasilnya adalah
vektor 1x1, yang berfungsi seperti bilangan real.


\>v.v'


    30

Ada juga fungsi norma (bersama dengan banyak fungsi Aljabar Linier
lainnya).


\>norm(v)^2


    30

Operator dan fungsi mematuhi bahasa matriks Euler.


Berikut ringkasan peraturannya.


* 
Suatu fungsi yang diterapkan pada vektor atau matriks diterapkan
* pada setiap elemen.

* 
Operator yang mengoperasikan dua matriks dengan ukuran yang sama
* diterapkan secara berpasangan pada elemen-elemen matriks.

* 
Jika kedua matriks mempunyai dimensi yang berbeda, keduanya
* diekspansi secara rasional sehingga mempunyai ukuran yang sama.


Misalnya, nilai skalar dikalikan vektor dengan mengalikan nilai setiap
elemen vektor. Atau matriks dikalikan vektor (dengan *, bukan .)
memperluas vektor ke ukuran matriks dengan menduplikasinya.


Berikut ini adalah kasus sederhana dengan operator ^.


\>[1,2,3]^2


    [1,  4,  9]

Ini kasus yang lebih rumit. Vektor baris dikalikan vektor kolom
memperluas keduanya dengan cara menduplikasi.


\>v:=[1,2,3]; v\*v'


                1             2             3 
                2             4             6 
                3             6             9 

Perhatikan bahwa perkalian skalar menggunakan perkalian matriks, bukan
*!


\>v.v'


    14

Ada banyak fungsi matriks. Kami memberikan daftar singkat. Anda harus
membaca dokumentasi untuk informasi lebih lanjut tentang perintah ini.


  sum,prod menghitung jumlah dan hasil kali baris  
  cumsum,cumprod melakukan hal yang sama secara kumulatif  
  menghitung nilai ekstrem setiap baris  
  extreme mengembalikan vektor dengan informasi ekstrem  
  diag(A,i) mengembalikan diagonal ke-i  
  setdiag(A,i,v) mengatur diagonal ke-i  
  id(n) matriks identitas  
  det(A) determinan  
  charpoly(A) polinomial karakteristik  
  eigenvalues(A) nilai eigen  

\>v\*v, sum(v\*v), cumsum(v\*v)


    [1,  4,  9]
    14
    [1,  5,  14]

Operator : menghasilkan vektor baris dengan spasi yang sama, opsional
dengan ukuran langkah.


\>1:4, 1:2:10


    [1,  2,  3,  4]
    [1,  3,  5,  7,  9]

Untuk menggabungkan matriks dan vektor terdapat operator "|" dan "_".


\>[1,2,3]|[4,5], [1,2,3]\_1


    [1,  2,  3,  4,  5]
                1             2             3 
                1             1             1 

Elemen-elemen matriks disebut dengan "A[i,j]".


\>A:=[1,2,3;4,5,6;7,8,9]; A[2,3]


    6

Untuk vektor baris atau kolom, v[i] adalah elemen ke-i dari vektor
tersebut. Untuk matriks, ini mengembalikan baris ke-i yang lengkap
dari matriks tersebut.


\>v:=[2,4,6,8]; v[3], A[3]


    6
    [7,  8,  9]

Indeks juga dapat berupa vektor baris dari indeks. : menunjukkan semua
indeks.


\>v[1:2], A[:,2]


    [2,  4]
                2 
                5 
                8 

Bentuk kependekan dari : menghilangkan indeks sepenuhnya.


\>A[,2:3]


                2             3 
                5             6 
                8             9 

Untuk tujuan vektorisasi, elemen matriks dapat diakses seolah-olah
elemen tersebut adalah vektor.


\>A{4}


    4

Matriks juga dapat diratakan menggunakan fungsi redim(). Ini
diimplementasikan dalam fungsi flatten().


\>redim(A,1,prod(size(A))), flatten(A)


    [1,  2,  3,  4,  5,  6,  7,  8,  9]
    [1,  2,  3,  4,  5,  6,  7,  8,  9]

Untuk menggunakan matriks pada tabel, mari kita atur ulang ke format
default, dan hitung tabel nilai sinus dan kosinus. Perhatikan bahwa
sudut dinyatakan dalam radian secara default.


\>defformat; w=0°:45°:360°; w=w'; deg(w)


                0 
               45 
               90 
              135 
              180 
              225 
              270 
              315 
              360 

Sekarang kita menambahkan kolom ke matriks.


\>M = deg(w)|w|cos(w)|sin(w)


                0             0             1             0 
               45      0.785398      0.707107      0.707107 
               90        1.5708             0             1 
              135       2.35619     -0.707107      0.707107 
              180       3.14159            -1             0 
              225       3.92699     -0.707107     -0.707107 
              270       4.71239             0            -1 
              315       5.49779      0.707107     -0.707107 
              360       6.28319             1             0 

Dengan menggunakan bahasa matriks, kita dapat menghasilkan beberapa
tabel dari beberapa fungsi sekaligus.


Dalam contoh berikut, kita menghitung t[j]^i untuk i dari 1 hingga n.
Kita mendapatkan sebuah matriks, yang setiap barisnya merupakan tabel
t^i untuk satu i. Artinya, matriks memiliki elemen latex: a_{i,j} =
t_j^i, \quad 1 \le j \le 101, \quad 1 \le i \le n


Fungsi yang tidak berfungsi untuk masukan vektor harus "divektorkan".
Hal ini dapat dicapai dengan kata kunci "map" dalam definisi fungsi.
Kemudian fungsi tersebut akan dievaluasi untuk setiap elemen parameter
vektor.


Integrasi numerik integral() hanya berfungsi untuk batas interval
skalar. Jadi kita perlu membuat vektorisasinya.


\>function map f(x) := integrate("x^x",1,x)


Kata kunci "map" membuat vektorisasi fungsi tersebut. Fungsinya
sekarang akan berfungsi untuk vektor bilangan.


\>f([1:5])


    [0,  2.05045,  13.7251,  113.336,  1241.03]

# Contoh lainnya

\>F=[3,3 ;-1,-1]


                3             3 
               -1            -1 

\>F'


                3            -1 
                3            -1 

\>F\*F'


                9            -3 
               -3             1 

\>sum(F\*F')


                6 
               -2 

\>defformat; g=0°:30°:180°; g=g'; deg(g)


                0 
               30 
               60 
               90 
              120 
              150 
              180 

# Sub-Matriks dan Matriks-Elemen

Untuk mengakses elemen matriks, gunakan notasi braket.


\>A=[1,2,3;4,5,6;7,8,9], A[2,2]


                1             2             3 
                4             5             6 
                7             8             9 
    5

Kita dapat mengakses baris matriks secara lengkap.


\>A[2]


    [4,  5,  6]

Dalam kasus vektor baris atau kolom, ini mengembalikan elemen vektor.


\>v=1:3; v[2]


    2

Untuk memastikan, Anda mendapatkan baris pertama untuk matriks 1xn dan
mxn, tentukan semua kolom menggunakan indeks kedua yang kosong.


\>A[2,]


    [4,  5,  6]

Jika indeks adalah vektor dari indeks, Euler akan mengembalikan baris
matriks yang sesuai.


Di sini kita menginginkan baris pertama dan kedua A.


\>A[[1,2]]


                1             2             3 
                4             5             6 

Kita bahkan dapat menyusun ulang A menggunakan vektor indeks.
Tepatnya, kita tidak mengubah A di sini, namun menghitung versi A yang
disusun ulang.


\>A[[3,2,1]]


                7             8             9 
                4             5             6 
                1             2             3 

Trik indeks berfungsi juga untuk kolom.


Contoh ini memilih semua baris A dan kolom kedua dan ketiga.


\>A[1:3,2:3]


                2             3 
                5             6 
                8             9 

Untuk singkatan ":" menunjukkan semua indeks baris atau kolom.


\>A[:,3]


                3 
                6 
                9 

Alternatifnya, biarkan indeks pertama kosong.


\>A[,2:3]


                2             3 
                5             6 
                8             9 

Kita juga bisa mendapatkan baris terakhir A.


\>A[-1]


    [7,  8,  9]

Sekarang mari kita ubah elemen A dengan menetapkan submatriks A ke
beberapa nilai. Ini sebenarnya mengubah matriks A yang disimpan.


\>A[1,1]=4


                4             2             3 
                4             5             6 
                7             8             9 

Kita juga dapat memberikan nilai pada baris A.


\>A[1]=[-1,-1,-1]


               -1            -1            -1 
                4             5             6 
                7             8             9 

Kita bahkan dapat menetapkan sub-matriks jika ukurannya sesuai.


\>A[1:2,1:2]=[5,6;7,8]


                5             6            -1 
                7             8             6 
                7             8             9 

Selain itu, beberapa jalan pintas diperbolehkan.


\>A[1:2,1:2]=0


                0             0            -1 
                0             0             6 
                7             8             9 

Peringatan: Indeks di luar batas mengembalikan matriks kosong, atau
pesan kesalahan, bergantung pada pengaturan sistem. Standarnya adalah
pesan kesalahan. Namun perlu diingat bahwa indeks negatif dapat
digunakan untuk mengakses elemen matriks yang dihitung dari akhir.


\>A[4]


    Row index 4 out of bounds!
    Error in:
    A[4] ...
        ^

# Contoh Lainnya

\>A=[-3,1,0; 0,2,-1; 5,0,4]


               -3             1             0 
                0             2            -1 
                5             0             4 

\>A[2]


    [0,  2,  -1]

\>B=A[[2,3,1]]


                0             2            -1 
                5             0             4 
               -3             1             0 

\>A[1]=5


                5             5             5 
                0             2            -1 
                5             0             4 

\>B[-2]


    [5,  0,  4]

\>A[5]


    Row index 5 out of bounds!
    Error in:
    A[5] ...
        ^

# Menyortir dan Mengacak

Fungsi sort() mengurutkan vektor baris.


\>sort([5,6,4,8,1,9])


    [1,  4,  5,  6,  8,  9]

Seringkali perlu mengetahui indeks vektor yang diurutkan dalam vektor
aslinya. Ini dapat digunakan untuk menyusun ulang vektor lain dengan
cara yang sama.


Mari kita mengacak sebuah vektor.


\>v=shuffle(1:10)


    [4,  5,  10,  6,  8,  9,  1,  7,  2,  3]

Indeks berisi urutan v.


\>{vs,ind}=sort(v); v[ind]


    [1,  2,  3,  4,  5,  6,  7,  8,  9,  10]

Ini juga berfungsi untuk vektor string.


\>s=["a","d","e","a","aa","e"]


    a
    d
    e
    a
    aa
    e

\>{ss,ind}=sort(s); ss


    a
    a
    aa
    d
    e
    e

Seperti yang Anda lihat, posisi entri ganda agak acak.


\>ind


    [4,  1,  5,  2,  6,  3]

Fungsi unik mengembalikan daftar elemen unik vektor yang diurutkan.


\>intrandom(1,10,10), unique(%)


    [9,  3,  8,  3,  5,  4,  10,  2,  5,  1]
    [1,  2,  3,  4,  5,  8,  9,  10]

Ini juga berfungsi untuk vektor string.


\>unique(s)


    a
    aa
    d
    e

# Contoh Lainnya

\>sort([-3, 5, 2, -1])


    [-3,  -1,  2,  5]

\>x=shuffle(2:8)


    [4,  2,  6,  8,  7,  3,  5]

\>y=["e", "t", "j", "g"]


    e
    t
    j
    g

\>sort(y)


    e
    g
    j
    t

\>intrandom (1,5,10)


    [7,  7,  10,  2,  10]

# Aljabar Linier

EMT memiliki banyak sekali fungsi untuk menyelesaikan masalah sistem
linier, sistem sparse, atau regresi.


Untuk sistem linier Ax=b, Anda dapat menggunakan algoritma Gauss,
matriks invers, atau linear fit. Operator A\b menggunakan versi
algoritma Gauss.


\>A=[1,2;3,4]; b=[5;6]; A\\b


               -4 
              4.5 

Contoh lain, kita membuat matriks berukuran 200x200 dan jumlah
baris-barisnya. Kemudian kita selesaikan Ax=b menggunakan matriks
invers. Kami mengukur kesalahan sebagai deviasi maksimal semua elemen
dari 1, yang tentu saja merupakan solusi yang tepat.


\>A=normal(200,200); b=sum(A); longest totalmax(abs(inv(A).b-1))


      2.110533969812423e-13 

Jika sistem tidak mempunyai solusi, kecocokan linier meminimalkan
norma kesalahan Ax-b.


\>A=[1,2,3;4,5,6;7,8,9]


                1             2             3 
                4             5             6 
                7             8             9 

Determinan matriks ini adalah 0.


\>det(A)


    0

# Contoh Lainnya

\>A=[4,0,-3; 1,1,1;-3,0,2]


                4             0            -3 
                1             1             1 
               -3             0             2 

\>det(A)


    -1

\>b=[4;5;0]


                4 
                5 
                0 

\>A\\b


               -8 
               25 
              -12 

\>inv(A)


               -2             0            -3 
                5             1             7 
               -3             0            -4 

\>A'\\b


               17 
                5 
               23 

# Matriks Simbolik

Maxima memiliki matriks simbolik. Tentu saja Maxima dapat digunakan
untuk permasalahan aljabar linier sederhana seperti itu. Kita dapat
mendefinisikan matriks untuk Euler dan Maxima dengan &amp;:=, lalu
menggunakannya dalam ekspresi simbolik. Bentuk [...] yang biasa untuk
mendefinisikan matriks dapat digunakan di Euler untuk mendefinisikan
matriks simbolik.


\>A &= [a,1,1;1,a,1;1,1,a]; $A


$$\begin{pmatrix}a & 1 & 1 \\ 1 & a & 1 \\ 1 & 1 & a \\ \end{pmatrix}$$\>$&det(A), $&factor(%)


$$\left(a-1\right)^2\,\left(a+2\right)$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-124.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-124.png)

\>$&invert(A) with a=0


$$\begin{pmatrix}-\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\ \frac{1  }{2} & -\frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} & -  \frac{1}{2} \\ \end{pmatrix}$$\>A &= [1,a;b,2]; $A


$$\begin{pmatrix}1 & a \\ b & 2 \\ \end{pmatrix}$$Seperti semua variabel simbolik, matriks ini dapat digunakan dalam
ekspresi simbolik lainnya.


\>$&det(A-x\*ident(2)), $&solve(%,x)


$$\left[ x=\frac{3-\sqrt{4\,a\,b+1}}{2} , x=\frac{\sqrt{4\,a\,b+1}+3  }{2} \right] $$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-128.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-128.png)

Nilai eigen juga dapat dihitung secara otomatis. Hasilnya adalah
sebuah vektor dengan dua vektor nilai eigen dan multiplisitas.


\>$&eigenvalues([a,1;1,a])


$$\left[ \left[ a-1 , a+1 \right]  , \left[ 1 , 1 \right]  \right] $$Untuk mengekstrak vektor eigen tertentu memerlukan pengindeksan yang
cermat.


\>$&eigenvectors([a,1;1,a]), &%[2][1][1]


$$\left[ \left[ \left[ a-1 , a+1 \right]  , \left[ 1 , 1 \right]    \right]  , \left[ \left[ \left[ 1 , -1 \right]  \right]  , \left[   \left[ 1 , 1 \right]  \right]  \right]  \right] $$    
                                   [1, - 1]
    

Matriks simbolik dapat dievaluasi dalam Euler secara numerik sama
seperti ekspresi simbolik lainnya.


\>A(a=4,b=5)


                1             4 
                5             2 

Dalam ekspresi simbolik, gunakan with.


\>$&A with [a=4,b=5]


$$\begin{pmatrix}1 & 4 \\ 5 & 2 \\ \end{pmatrix}$$Akses ke deretan matriks simbolik berfungsi sama seperti matriks
numerik.


\>$&A[1]


$$\left[ 1 , a \right] $$Ekspresi simbolis dapat berisi tugas. Dan itu mengubah matriks A.


\>&A[1,1]:=t+1; $&A


$$\begin{pmatrix}t+1 & a \\ b & 2 \\ \end{pmatrix}$$Ada fungsi simbolik di Maxima untuk membuat vektor dan matriks. Untuk
ini, lihat dokumentasi Maxima atau tutorial tentang Maxima di EMT.


\>v &= makelist(1/(i+j),i,1,3); $v


$$\left[ \frac{1}{j+1} , \frac{1}{j+2} , \frac{1}{j+3} \right] $$\>B &:= [1,2;3,4]; $B, $&invert(B)


$$\begin{pmatrix}-2 & 1 \\ \frac{3}{2} & -\frac{1}{2} \\   \end{pmatrix}$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-136.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-136.png)

Hasilnya dapat dievaluasi secara numerik dalam Euler. Untuk informasi
lebih lanjut tentang Maxima, lihat pengenalan Maxima.


\>$&invert(B)()


               -2             1 
              1.5          -0.5 

Euler juga memiliki fungsi kuat xinv(), yang melakukan upaya lebih
besar dan mendapatkan hasil yang lebih tepat.


Perhatikan, bahwa dengan &amp;:= matriks B telah didefinisikan sebagai
simbolik dalam ekspresi simbolik dan numerik dalam ekspresi numerik.
Jadi kita bisa menggunakannya di sini.


\>longest B.xinv(B)


                          1                       0 
                          0                       1 

Misalnya. nilai eigen dari A dapat dihitung secara numerik.


\>A=[1,2,3;4,5,6;7,8,9]; real(eigenvalues(A))


    [16.1168,  -1.11684,  0]

Atau secara simbolis. Lihat tutorial tentang Maxima untuk detailnya.


\>$&eigenvalues(@A)


$$\left[ \left[ 3-\sqrt{10} , \sqrt{10}+3 , 1 \right]  , \left[ 1 , 1   , 1 \right]  \right] $$# Contoh Lainnya

\>A &= [2,6,4;1,2,3;4,5,6]; $A


$$\begin{pmatrix}2 & 6 & 4 \\ 1 & 2 & 3 \\ 4 & 5 & 6 \\ \end{pmatrix}$$\>$&det(A)


$$18$$\>B &= makelist(1/(i+j),i,1,3); $B


$$\left[ \frac{1}{j+1} , \frac{1}{j+2} , \frac{1}{j+3} \right] $$\>A &= [2,a;b,3]; $A


$$\begin{pmatrix}2 & a \\ b & 3 \\ \end{pmatrix}$$\>$&eigenvalues([b,2;4,a])


$$\left[ \left[ \frac{-\sqrt{b^2-2\,a\,b+a^2+32}+b+a}{2} , \frac{  \sqrt{b^2-2\,a\,b+a^2+32}+b+a}{2} \right]  , \left[ 1 , 1 \right]    \right] $$# Nilai Numerik dalam Ekspresi simbolik

Ekspresi simbolis hanyalah string yang berisi ekspresi. Jika kita
ingin mendefinisikan nilai untuk ekspresi simbolik dan ekspresi
numerik, kita harus menggunakan "&amp;:=".


\>A &:= [1,pi;4,5]


                1       3.14159 
                4             5 

Masih terdapat perbedaan antara bentuk numerik dan simbolik. Saat
mentransfer matriks ke bentuk simbolik, pendekatan pecahan untuk real
akan digunakan.


\>$&A


$$\begin{pmatrix}t+1 & a \\ b & 2 \\ \end{pmatrix}$$Untuk menghindari hal ini, ada fungsi "mxmset(variabel)".


\>mxmset(A); $&A


$$\begin{pmatrix}1 & 8 \\ 4 & 9 \\ \end{pmatrix}$$Maxima juga dapat menghitung dengan bilangan floating point, bahkan
dengan floating point besar dengan 32 digit. Namun, evaluasinya jauh
lebih lambat.


\>$&bfloat(sqrt(2)), $&float(sqrt(2))


$$1.414213562373095$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-146.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-146.png)

Ketepatan angka floating point besar dapat diubah.


\>&fpprec:=100; &bfloat(pi)


    
            3.14159265358979323846264338327950288419716939937510582097494\
    4592307816406286208998628034825342117068b0
    

Variabel numerik dapat digunakan dalam ekspresi simbolik apa pun
menggunakan "@var".


Perhatikan bahwa ini hanya diperlukan, jika variabel telah
didefinisikan dengan ":=" atau "=" sebagai variabel numerik.


\>B:=[1,pi;3,4]; $&det(@B)


$$-5.424777960769379$$# Contoh Lainnya

\>A &:= [1,8;4,9]


                1             8 
                4             9 

\>$&bfloat(sqrt(5)) 


$$2.2360679774997896964091736687313_B \times 10^{0}$$\>$&float(sqrt(5))


$$2.23606797749979$$\>mxmset(A); $&A


$$\begin{pmatrix}1 & 8 \\ 4 & 9 \\ \end{pmatrix}$$\>$& det(@A)


$$-23$$# Demo - Suku Bunga

Di bawah ini, kami menggunakan Euler Math Toolbox (EMT) untuk
menghitung suku bunga. Kami melakukannya secara numerik dan simbolis
untuk menunjukkan kepada Anda bagaimana Euler dapat digunakan untuk
memecahkan masalah kehidupan nyata.


Asumsikan Anda memiliki modal awal sebesar 5.000 (katakanlah dalam
dolar).


\>K=5000


    5000

Sekarang kami mengasumsikan tingkat bunga 3% per tahun. Mari kita
tambahkan satu tarif sederhana dan hitung hasilnya.


\>K\*1.03


    5150

Euler juga akan memahami sintaks berikut.


\>K+K\*3%


    5150

Namun lebih mudah menggunakan faktor tersebut.


\>q=1+3%, K\*q


    1.03
    5150

Selama 10 tahun, kita cukup mengalikan faktor-faktornya dan
mendapatkan nilai akhir dengan tingkat bunga majemuk.


\>K\*q^10


    6719.58189672

Untuk keperluan kita, kita dapat mengatur format menjadi 2 digit
setelah titik desimal.


\>format(12,2); K\*q^10


        6719.58 

Mari kita cetak yang dibulatkan menjadi 2 digit dalam satu kalimat
lengkap.


\>"Starting from " + K + "$ you get " + round(K\*q^10,2) + "$."


    Starting from 5000$ you get 6719.58$.

Bagaimana jika kita ingin mengetahui hasil antara dari tahun 1 sampai
tahun ke 9? Untuk ini, bahasa matriks Euler sangat membantu. Anda
tidak perlu menulis satu perulangan, tetapi cukup masuk


\>K\*q^(0:10)


    Real 1 x 11 matrix
    
        5000.00     5150.00     5304.50     5463.64     ...

Bagaimana keajaiban ini terjadi? Pertama, ekspresi 0:10 mengembalikan
vektor bilangan bulat.


\>short 0:10


    [0,  1,  2,  3,  4,  5,  6,  7,  8,  9,  10]

Kemudian semua operator dan fungsi di Euler dapat diterapkan pada
vektor elemen demi elemen. Jadi


\>short q^(0:10)


    [1,  1.03,  1.0609,  1.0927,  1.1255,  1.1593,  1.1941,  1.2299,
    1.2668,  1.3048,  1.3439]

adalah vektor faktor q^0 sampai q^10. Ini dikalikan dengan K, dan kita
mendapatkan vektor nilainya.


\>VK=K\*q^(0:10);


Tentu saja, cara realistis untuk menghitung suku bunga ini adalah
dengan membulatkan ke sen terdekat setiap tahunnya. Mari kita
tambahkan fungsi untuk ini.


\>function oneyear (K) := round(K\*q,2)


Mari kita bandingkan kedua hasil tersebut, dengan dan tanpa
pembulatan.


\>longest oneyear(1234.57), longest 1234.57\*q


                    1314.82 
                 1314.81705 

Sekarang tidak ada rumus sederhana untuk tahun ke-n, dan kita harus
mengulanginya selama bertahun-tahun. Euler memberikan banyak solusi
untuk ini.


Cara termudah adalah fungsi iterate, yang mengulangi fungsi tertentu
beberapa kali.


\>VKr=iterate("oneyear",5000,10)


    Real 1 x 11 matrix
    
        5000.00     5325.00     5671.13     6039.75     ...

Kami dapat mencetaknya dengan cara yang ramah, menggunakan format kami
dengan tempat desimal tetap.


\>VKr'


        5000.00 
        5325.00 
        5671.13 
        6039.75 
        6432.33 
        6850.43 
        7295.71 
        7769.93 
        8274.98 
        8812.85 
        9385.69 

Untuk mendapatkan elemen vektor tertentu, kami menggunakan indeks
dalam tanda kurung siku.


\>VKr[2], VKr[1:3]


        5325.00 
        5000.00     5325.00     5671.13 

Anehnya, kita juga bisa menggunakan vektor indeks. Ingatlah bahwa 1:3
menghasilkan vektor [1,2,3].


Mari kita bandingkan elemen terakhir dari nilai yang dibulatkan dengan
nilai penuh.


\>VKr[-1], VK[-1]


        9385.69 
      153925.27 

Perbedaannya sangat kecil.


# Contoh Lainnya

Akan digunakan formula berikut untuk menyelesaikan soal


$$S = P [\frac {(1+ \frac {r}{12})^{12\times t}-1}{\frac{r}{12}}]$$James menyetorkan $250 setiap bulannya ke rekening pensiun dimulai


saat ia berusia 40 tahun. Jika investasi ini menghasilkan bunga 5%


setiap tahunnya, berapa jumlah total tabungan pensiun James 27 tahun


kemudian?


Dari soal tersebut diketahui nilai


P = $250


t = 27 tahun


r = 5% = 0.05


\>K=250


         250.00 

\>q=1+5%, K\*q 


           1.05 
         262.50 

\>format(12,2); K\*q^(27)


         933.36 

\>short q^(0:10)


    [1,  1.05,  1.1025,  1.1576,  1.2155,  1.2763,  1.3401,  1.4071,
    1.4775,  1.5513,  1.6289]

\>function oneyear (K) := round(K\*q,2)

\>longest oneyear(1234.57)


                     1296.3 

\>VKr=iterate("oneyear",250,27)


    Real 1 x 28 matrix
    
         250.00      262.50      275.63      289.41     ...

\>VKr[27]


         888.95 

\>VKr[-1], VK[-1]


         933.40 
      153925.27 

Karena dengan cara sesuai contoh saya belum menemukan hasilnya, maka
saya mnegerjakan sesuai formula yang terdapat di petunjuk


\>P:=250; t:=27; r:=0.05; S= P\*[((1+r/12)^(12\*t)-1)/(r/12)]


      170797.30 

Jadi, total uang tabungan pensiun James 27 tahun kemudian adalah
$170,797.30


Kayla menyetorkan $100 ke rekening pensiun sejak ia berusia 25 tahun.
Jika investasi ini menghasilkan bunga 4% per tahun, dihitung secara
bulanan, berapa banyak uang yang akan terkumpul di rekening Kayla
ketika ia pensiun di usia 65 tahun?


Dari soal tersebut diketahui nilai


P = $100


t = 65-25 = 40 tahun


r = 4% = 0.04


\>P:=100; t:=40; r:=0.04; S= P\*[((1+r/12)^(12\*t)-1)/(r/12)]


      118196.13 

Jadi, banyak uang yang akan terkumpul di rekening Kayla ketika ia
pensiun di usia 65 tahun adalah $118,196.13


Sue dan Richard ingin membuat dana kuliah untuk putri mereka yang akan
terkumpul sebesar $120,000 pada akhir 18 tahun. Jika mereka
mengandalkan suku bunga 3%, dihitung setiap bulan, berapa banyak yang
harus mereka setorkan setiap bulan untuk mencapai target tersebut?


Dari soal tersebut diketahui nilai


S = $120,000


t = 18 tahun


r = 3% = 0.03


\>S=120000; t=18; r=0.03; P=S /[((1+r/12)^(12\*t)-1)/(r/12)]


         419.67 

Jadi, banyak uang yang harus mereka setorkan setiap bulan untuk
mencapai target tersebut adalah $419.67


Lamont ingin memiliki tabungan pensiun sebesar $200,000 saat berusia
70 tahun. Jika ia mulai menyetorkan uang setiap bulan saat berusia 30
tahun dan mendapatkan bunga 4,5% per tahun, berapa banyak uang yang
harus dia simpan setiap bulan agar bisa mencapai target yang
diinginkan?


Dari soal tersebut diketahui nilai


S = $200,000


t = 70-30 = 40 tahun


r = 4.5% = 0.045


\> S=200000; t=40; r=0.045; P=S /[((1+r/12)^(12\*t)-1)/(r/12)]


         149.13 

Jadi, banyak uang yang harus dia simpan setiap bulan agar bisa
mencapai target yang diinginkan adalah $149.13


# Memecahkan Persamaan

Sekarang kita mengambil fungsi yang lebih maju, yang menambahkan
tingkat uang tertentu setiap tahunnya.


\>function onepay (K) := K\*q+R


Kita tidak perlu menentukan q atau R untuk definisi fungsi. Hanya jika
kita menjalankan perintah, kita harus mendefinisikan nilai-nilai ini.
Kami memilih R=200.


\>R=200; iterate("onepay",5000,10)


    Real 1 x 11 matrix
    
        5000.00     5450.00     5922.50     6418.63     ...

Bagaimana jika kita menghapus jumlah yang sama setiap tahun?


\>R=-200; iterate("onepay",5000,10)


    Real 1 x 11 matrix
    
        5000.00     5050.00     5102.50     5157.63     ...

Kami melihat uangnya berkurang. Jelasnya, jika kita hanya mendapat
bunga sebesar 150 pada tahun pertama, namun menghapus 200, kita
kehilangan uang setiap tahunnya.


Bagaimana kita dapat menentukan berapa tahun uang tersebut akan
bertahan? Kita harus menulis satu lingkaran untuk ini. Cara termudah
adalah dengan melakukan iterasi cukup lama.


\>VKR=iterate("onepay",5000,50)


    Real 1 x 51 matrix
    
        5000.00     5050.00     5102.50     5157.63     ...

Dengan menggunakan bahasa matriks, kita dapat menentukan nilai negatif
pertama dengan cara berikut.


\>min(nonzeros(VKR<0))


           0.00 

Alasannya adalah bukan nol (VKR&lt;0) mengembalikan vektor indeks i,
dengan VKR[i]&lt;0, dan min menghitung indeks minimal.


Karena vektor selalu dimulai dengan indeks 1, maka jawabannya adalah
47 tahun.


Fungsi iterate() memiliki satu trik lagi. Ini dapat mengambil kondisi
akhir sebagai argumen. Kemudian akan mengembalikan nilai dan jumlah
iterasi.


\>{x,n}=iterate("onepay",5000,till="x<0"); x, n,


    User interrupted!
    onepay:
        useglobal; return K*q+R 
    Try "trace errors" to inspect local variables after errors.
    iterate:
        xn=f$(x,args());

Mari kita coba menjawab pertanyaan yang lebih ambigu. Asumsikan kita
mengetahui bahwa nilainya adalah 0 setelah 50 tahun. Berapa tingkat
bunganya?


Ini adalah pertanyaan yang hanya bisa dijawab secara numerik. Di bawah
ini, kita akan mendapatkan rumus yang diperlukan. Kemudian Anda akan
melihat bahwa tidak ada rumus yang mudah untuk menentukan tingkat suku
bunga. Namun untuk saat ini, kami menargetkan solusi numerik.


Langkah pertama adalah mendefinisikan fungsi yang melakukan iterasi
sebanyak n kali. Kami menambahkan semua parameter ke fungsi ini.


\>function f(K,R,P,n) := iterate("x\*(1+P/100)+R",K,n;P,R)[-1]


Iterasinya sama seperti di atas


$$x_{n+1} = x_n \cdot \left(1+ \frac{P}{100}\right) + R$$Namun kami tidak lagi menggunakan nilai global R dalam ekspresi kami.
Fungsi seperti iterate() memiliki trik khusus di Euler. Anda dapat
meneruskan nilai variabel dalam ekspresi sebagai parameter titik koma.
Dalam hal ini P dan R.


Apalagi kami hanya tertarik pada nilai terakhir. Jadi kita ambil
indeks [-1].


Mari kita coba tes.


\>f(5000,-200,3,47)


         -19.83 

Sekarang kita bisa menyelesaikan masalah kita.


\>solve("f(5000,-200,x,50)",3)


           3.15 

Rutinitas penyelesaian menyelesaikan ekspresi=0 untuk variabel x.
Jawabannya adalah 3,15% per tahun. Kami mengambil nilai awal 3% untuk
algoritma. Fungsi solve() selalu membutuhkan nilai awal.


Kita dapat menggunakan fungsi yang sama untuk menyelesaikan pertanyaan
berikut: Berapa banyak yang dapat kita keluarkan per tahun sehingga
modal awal habis setelah 20 tahun dengan asumsi tingkat bunga 3% per
tahun.


\>solve("f(5000,x,3,20)",-200)


Perhatikan bahwa Anda tidak dapat menyelesaikan jumlah tahun, karena
fungsi kami mengasumsikan n sebagai nilai bilangan bulat.


# Contoh lainnya

\>function onepay (K) := K\*q+R

\>R=5%; iterate("onepay",250,27)


    Real 1 x 28 matrix
    
         250.00      262.55      275.73      289.56     ...

\>function f(K,R,P,n) := iterate("x\*(1+P/100)+R",K,n;P,R)[-1]

\>f(250,-20,3,16)


          -1.96 

\>solve("f(250,-20,x,16)",3)


           3.06 

## Solusi Simbolis Masalah Suku Bunga

Kita dapat menggunakan bagian simbolis dari Euler untuk mempelajari
masalahnya. Pertama kita mendefinisikan fungsi onepay() kita secara
simbolis.


\>function op(K) &= K\*q+R; $&op(K)


$$R+q\,K$$Sekarang kita dapat mengulanginya.


\>$&op(op(op(op(K)))), $&expand(%)


$$q^3\,R+q^2\,R+q\,R+R+q^4\,K$$![images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-156.png](images/EMT4aljabar%20-%20Naila%20Khalidatus%20Salwa-156.png)

Kami melihat sebuah pola. Setelah n periode yang kita miliki


$$K_n = q^n K + R (1+q+\ldots+q^{n-1}) = q^n K + \frac{q^n-1}{q-1} R$$Rumusnya adalah rumus jumlah geometri yang diketahui Maxima.


\>&sum(q^k,k,0,n-1); $& % = ev(%,simpsum)


$$\sum_{k=0}^{n-1}{q^{k}}=\frac{q^{n}-1}{q-1}$$Ini agak rumit. Jumlahnya dievaluasi dengan tanda "simpsum" untuk
menguranginya menjadi hasil bagi.


Mari kita membuat fungsi untuk ini.


\>function fs(K,R,P,n) &= (1+P/100)^n\*K + ((1+P/100)^n-1)/(P/100)\*R; $&fs(K,R,P,n)


$$\frac{100\,\left(\left(\frac{P}{100}+1\right)^{n}-1\right)\,R}{P}+K  \,\left(\frac{P}{100}+1\right)^{n}$$Fungsinya sama dengan fungsi f kita sebelumnya. Tapi ini lebih
efektif.


\>longest f(5000,-200,3,47), longest fs(5000,-200,3,47)


         -19.82504734650985 
         -19.82504734652684 

Sekarang kita dapat menggunakannya untuk menanyakan waktu n. Kapan
modal kita habis? Perkiraan awal kami adalah 30 tahun.


\>solve("fs(5000,-330,3,x)",30)


          20.51 

Jawaban ini mengatakan akan menjadi negatif setelah 21 tahun.


Kita juga dapat menggunakan sisi simbolis Euler untuk menghitung rumus
pembayaran.


Asumsikan kita mendapatkan pinjaman sebesar K, dan membayar n
pembayaran sebesar R (dimulai setelah tahun pertama) meninggalkan sisa
hutang sebesar Kn (pada saat pembayaran terakhir). Rumusnya jelas


\>equ &= fs(K,R,P,n)=Kn; $&equ


$$\frac{100\,\left(\left(\frac{P}{100}+1\right)^{n}-1\right)\,R}{P}+K  \,\left(\frac{P}{100}+1\right)^{n}={\it Kn}$$Biasanya rumus ini diberikan dalam bentuk


$$i = \frac{P}{100}$$\>equ &= (equ with P=100\*i); $&equ


$$\frac{\left(\left(i+1\right)^{n}-1\right)\,R}{i}+\left(i+1\right)^{  n}\,K={\it Kn}$$Kita dapat menyelesaikan nilai R secara simbolis.


\>$&solve(equ,R)


$$\left[ R=\frac{i\,{\it Kn}-i\,\left(i+1\right)^{n}\,K}{\left(i+1  \right)^{n}-1} \right] $$Seperti yang Anda lihat dari rumusnya, fungsi ini mengembalikan
kesalahan floating point untuk i=0. Euler tetap merencanakannya.


Tentu saja, kami memiliki batasan berikut.


\>$&limit(R(5000,0,x,10),x,0)


$$\lim_{x\rightarrow 0}{R\left(5000 , 0 , x , 10\right)}$$Yang jelas tanpa bunga kita harus membayar kembali 10 tarif 500.


Persamaan tersebut juga dapat diselesaikan untuk n. Akan terlihat
lebih bagus jika kita menerapkan beberapa penyederhanaan padanya.


\>fn &= solve(equ,n) | ratsimp; $&fn


$$\left[ n=\frac{\log \left(\frac{R+i\,{\it Kn}}{R+i\,K}\right)}{  \log \left(i+1\right)} \right] $$## Contoh lainnya

Akan digunakan formula berikut untuk menyelesaikan soal


$$M = P [\frac {\frac {r}{12}(1+ \frac {r}{12})^n}{(1+\frac{r}{12})^n -1}]$$Harga sebuah rumah adalah $98,000 dengan uang muka $16,000. Jika suku
bunganya 6,5% dan jangka waktu pinjaman 25 tahun, berapa besar
angsuran bulanannya?


Dari soal diketahui nilai


P = $98,000-$16,000 = $82,000


r = 6.5% = 0.065


n = 25 tahun = 300 bulan


\>P = 82000; r = 6.5%; n = 300; P\*[((r/12)\*(1+ (r/12))^n)/((1+(r/12))^n -1)]


         553.67 

Jadi, besar angsuran bulanannya adalah $553.67


Harga sebuah rumah adalah $124,000 dengan uang muka $20,000. Jika suku
bunganya 5,5% dan jangka waktu peminjaman 30 tahun, berapa besar
angsuran tiap bulannya?


Dari soal diketahui nilai


P = $124,000 - $20,000 = $104,000


r = 5,5%


n = 30 tahun = 360 bulan


\>P = 104000; r = 5.5%; n = 360; P\*[((r/12)\*(1+ (r/12))^n)/((1+(r/12))^n -1)]


         590.50 

Jadi, besar angsuran bulanannya adalah $590.50 


Harga sebuah rumah adalah $135,000 dengan uang muka $18,000. Jika suku
bunganya 7.75% dan jangka waktu pinjaman 20 tahun, berapa besar
angsuran bulanan yang harus dibayarkan?


Dari soal diketahui nilai


P = $135,000 - $18,000 = $117,000


r = 7.75%


N = 20 tahun = 240 bulan


\> P = 117000; r = 7.75%; n = 240; P\*[((r/12)\*(1+ (r/12))^n)/((1+(r/12))^n -1)]


         853.79 

Jadi, besar angsuran bulanannya adalah $853.79


Harga sebuah rumah adalah $151,000 dengan uang muka $21,000. Jika
bunganya 6,25% dan jangka waktu pinjaman 25 tahun, berapa besar
angsuran bulanannya?


Dari soal diketahui nilai


P = $151,000 - $21,000 = $130,000


r = 6,25%


n = 25 tahun = 300 bulan


\>P = 130000; r = 6.25%; n = 300; P\*[((r/12)\*(1+ (r/12))^n)/((1+(r/12))^n -1)]


         857.57 

Jadi, besar angsuran bulanannya $857.57 


\>//    

