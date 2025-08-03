About
=====
This repository provides a Bash script fragment [better_tux.txt](better_tux.txt) to display an improved Tux logo-image in **neofetch**.

Preview
=====
<img width="1920" height="1080" alt="better_tux_screenshot" src="https://github.com/user-attachments/assets/2506d13e-311b-4afa-a996-060021a0be4e" />

Configuration Guide
=====

After installing [neofetch](https://github.com/dylanaraps/neofetch.git)

## From Terminal
1. **Download txt file [better_tux.txt](better_tux.txt) from github repository using git:**
   ```
   git clone https://github.com/dominikx2002/better_tux.git
   ```
   ```
   cd better_tux
   ```

2. **Config neofetch script**
Make changes using sed tool with this single command:
   ```
   sudo sed -i '/^ *"Hash"\*)/e cat better_tux.txt' /usr/bin/neofetch
   ```

3. **Edit neofetch configuration**  
Edit config file with single command:
   ```
   sed -i 's/^ascii_distro="auto"/ascii_distro="better_tux"/' ~/.config/neofetch/config.conf
   ```
**Run neofetch**  
```
neofetch
```
---

## Manual configuration

**1. Copy script fragment:**
```bash
        "better_tux")
            set_colors 220 8 250 11 7 235 
            read -rd '' ascii_data <<'EOF'
${c6}                      .${c2};:ccc;${c6}'                    
${c6}                   .${c2}:llllllllll;${c6}.                 
${c2}                  :llllllllllllll${c6};                
${c6}                 ;${c2}llllllllllllllll${c6}.               
${c2}                 llodllllokOkollllc               
${c2}                 l${c3}OMWN${c2}olo${c3}WNKWW${c2}dllll               
${c2}                 l${c3}N${c2}xo${c3}X${c2}xox${c3}N${c2}olk${c3}M${c2}0llll               
${c2}                 cxO${c4}xO${c1}000${c4}Okx${c2}OKollll               
${c2}                 l${c4}xO${c1}00000000${c4}O${c1}0${c4}d${c2}llll               
${c6}                .${c2}ld${c4}kOOOOOOOOOO${c2}Ollll:              
${c2}                clx${c5}M${c3}X${c4}0OOO0K${c3}X${c5}WMM${c3}k${c2}llll:             
${c6}              .${c2}cll${c3}X${c5}MMMMMMMMMMMMW${c2}dllllc${c6}.           
${c2}             ,lll${c3}O${c5}MMMMMMMMMMMMMMN${c2}olllll:          
${c6}           .${c2}clllx${c5}MMMMMMMMMMMMMMMM${c3}X${c2}ll${c3}d${c2}olll${c6}'        
${c6}          '${c2}lodlx${c5}MMMMMMMMMMMMMMMMMM${c3}X${c2}ll${c3}dd${c2}lll:       
${c2}         ;ldxld${c5}WMMMMMMMMMMMMMMMMMMMX${c2}ll${c3}dx${c2}lllc      
${c2}        :ll${c3}O${c2}lo${c5}WMMMMMMMMMMMMMMMMMMMMM${c3}K${c2}ll${c3}Ko${c2}lll:     
${c6}       .${c2}ll${c3}kk${c2}l${c3}X${c5}MMMMMMMMMMMMMMMMMMMMMMM${c3}k${c2}l${c3}0k${c2}llll${c6}.    
${c2}       lll${c3}O0${c2}d${c5}MMMMMMMMMMMMMMMMMMMMMMMMX${c3}O${c5}N${c3}O${c2}olll${c6}'    
${c2}       lllo${c5}XXMMMMMMMMMMMMMMMMMMMMMMM${c3}x${c2}lllo${c3}xkx${c2}l${c6}.    
${c4}       xkkx${c2}o${c3}kX${c5}MMMMMMMMMMMMMMMMMMMMM${c4}X${c2}ollllll${c3}O${c2}:     
${c4}     .x${c1}0000O${c2}olo${c3}kN${c5}MMMMMMMMMMMMMMMMM${c4}X${c1}0O${c4}d${c2}ooo${c4}x${c1}O0O${c4}o    
${c4}  :d${c1}O00000000${c4}d${c2}lll${c3}xN${c5}MMMMMMMMMMMMMMM${c1}000000000000${c4}:   
${c4} ;${c1}000000000000${c4}x${c2}lll${c3}o${c5}WMMMMMMMMMMMMMM${c1}0000000000000${c4},  
${c4} .${c1}0000000000000${c4}O${c3}kOK${c5}MMMMMMMMMMMMMM${c3}N${c1}00000000000000${c4}o 
${c4} c${c1}0000000000000000${c3}0N${c5}MMMMMMMMMM${c3}X0${c4}x${c1}O000000000000${c4}d   
${c1} d0000000000000000k${c2}lo${c3}xOO0OOkd${c2}lll${c4}x${c1}0000000000       
${c4}         ;${c1}00000000${c4}'             .${c1}00000000         
                                   00${c4},
EOF
    ;;
```
or from text file [better_tux.txt](better_tux.txt) located in this repository.

2. **Config neofetch script**

Open the neofetch script located at /usr/bin/neofetch using a text editor with root privileges, for example:
   ```
   sudo nano /usr/bin/neofetch
   ```

Find the function called *get_distro_ascii()*:
   Find: Ctrl + W
   Type: `get_distro_ascii()`
   
Within this function, between other `case` entries, paste the copied code
Make sure to place it among the other distro cases.

Save your changes and close the text editor:
   Save: Ctrl + O, Enter
   Exit: Ctrl + X

3. **Edit neofetch configuration**  
Open your neofetch config file:
   ```
   nano ~/.config/neofetch/config.conf
   ```
   
Find the line `ascii_distro="auto"`:
   Find: Ctrl + W
   Type: ascii_distro="auto"
and replace it with `ascii_distro="better_tux"`

Save the config file and exit the editor:

   Save: Ctrl + O, Enter
   Exit: Ctrl + X
   
**Run neofetch**  
```
neofetch
```
   
---

Created by [Dominik Serafin/dominikx2002]
