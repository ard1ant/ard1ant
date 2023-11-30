
#!/bin/bash

# Fungsi untuk memeriksa aktivitas mencurigakan
check_security_activity() {
    # Tempatkan logika deteksi serangan siber di sini
    # Contoh sederhana: memeriksa log untuk string mencurigakan
    if grep -q "mencurigakan" /var/log/security.log; then
        echo -e "\e[1;31mWARNING: Aktivitas mencurigakan terdeteksi!\e[m"
    fi
}

# Fungsi untuk menampilkan prompt
custom_prompt() {
    PS1="\[\e[1;35m\] * ( * \[\e[1;36m\]( \` )\\ ) ( \` ( ( \[\e[1;33m\])\\))( ( (())/( ( )\\))( )\\ )\\ \[\e[1;32m\])\[\e[1;31m\]((_)()\\ )( /(_)) )\\((_)()((((_))))\[\e[1;34m\](((((_)(\[\e[1;37m\] \n   | \[\e[1;34m\]\/ |((_) | _ \\ | | | \\/ (_)_\\(_|_)_\\(_)\[\e[1;35m\]\n   | |\\/| | '_| | _/ |_| | |\\/| |/ _ \\ / _ \\   \n   \[\e[1;36m\]|_| |_|_| |_| \\\___/|_| |_/_/ \\_\\/ \\_\\ \n   \[\e[1;37m\]\n   Current Time: \[\e[1;32m\]\$(date +'%T')\[\e[1;37m\] | \[\e[1;36m\]Your Location: \[\e[1;32m\]\$(curl -s https://ipinfo.io/city), \$(curl -s https://ipinfo.io/region)\[\e[1;37m\] | \[\e[1;36m\]Your IP: \[\e[1;32m\]\$(curl -s https://ipinfo.io/ip)\[\e[1;37m\] | \[\e[1;36m\]VPN Status: \[\e[1;32m\]\$(ifconfig tun0 >/dev/null 2>&1 && echo "Connected" || echo "Not Connected")\[\e[m\]"
}

# Panggil fungsi pemantauan keamanan pada setiap prompt
PROMPT_COMMAND="check_security_activity; $PROMPT_COMMAND"

# Panggil fungsi untuk menetapkan prompt kustom
custom_prompt


export PS1='\[\e[1;32m\]{π} \[\e[1;33m\]Mr PUMA\[\e[m\]\n\[\e[1;34m\]\e[1m➤➤➤ \[\e[m\]'
