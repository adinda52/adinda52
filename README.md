- .MODEL SMALL  ; Model memori kecil
.STACK 10H    ; Ukuran stack

.DATA         ; Segmen data
OutputHex DB 'Output angka dalam format Hexadecimal: ', '$' ; Teks yang ingin ditampilkan
HexValue DB 'FF', '$'   ; Nilai heksadesimal yang ingin ditampilkan

.CODE         ; Segmen kode
START:
    MOV AX, @DATA  ; Inisialisasi segment data
    MOV DS, AX

    ; Menampilkan teks output
    LEA DX, OutputHex  ; Memuat alamat OutputHex ke DX
    MOV AH, 09H        ; Fungsi DOS untuk mencetak string
    INT 21H            ; Panggil interrupt untuk menampilkan string

    ; Menampilkan nilai heksadesimal
    LEA DX, HexValue   ; Memuat alamat HexValue ke DX
    MOV AH, 09H        ; Fungsi DOS untuk mencetak string
    INT 21H            ; Panggil interrupt untuk menampilkan string

    ; Mengakhiri program
    MOV AH, 4CH        ; Fungsi DOS untuk keluar program
    INT 21H            ; Panggil interrupt untuk keluar

END START  ; Akhir program
