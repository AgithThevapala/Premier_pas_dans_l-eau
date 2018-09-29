# Premier_pas_dans_l-eau

from datetime import datetime

result = input("Saisir une date sous la forme JJMMAAAA : ")
date = datetime.strptime(result, '%d%m%Y')
iAA = int(date.strftime('%y'))
iDay = int(date.strftime('%d'))
iMonth = int(date.strftime('%m'))
isBissex = False

iCal = (iAA + (iAA / 4))

iCal += iDay

if 2 == iMonth:
    iCal += 3
elif iMonth == 3:
    iCal += 3
elif iMonth == 4:
    iCal += 6
elif iMonth == 5:
    iCal += 1
elif iMonth == 6:
    iCal += 4
elif iMonth == 7:
    iCal += 6
elif iMonth == 8:
    iCal += 2
elif iMonth == 9:
    iCal += 5
elif iMonth == 11:
    iCal += 3
elif iMonth == 12:
    iCal += 5

iYear = int(date.strftime('%Y'))

if iYear % 400 == 0:
    isBissex = True
elif iYear % 100 == 0:
    isBissex = False
elif iYear % 4 == 0:
    isBissex = True

if isBissex:
    if iMonth == 1 or iMonth == 2:
        iCal = iCal - 1


tmp = iYear - iAA
if tmp == 1600:
    iCal += 6
elif tmp == 1700:
    iCal += 4
elif tmp == 1800:
    iCal += 2
elif tmp == 1900:
    iCal += 0
elif tmp == 2000:
    iCal += 6
elif tmp == 2100:
    iCal += 4

iCal = iCal % 7

listJ = ["Dimanche", "Lundi", "Mardi", "Mercredi", "Jeudi", "Vendredi", "Samedi"]

indx = len(listJ)
for i in range(len(listJ)):
    if i == int(iCal):
        print("Le jour de la semaine Gregorienne correpondant à la date indiqué est le :", listJ[i])
        break
