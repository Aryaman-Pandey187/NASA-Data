# NASA-Data
Hello, this is a simple program that retrieves data through an API and displays them, feel free to use the code for any of your projects. 

Here is the code:


import requests
while True:
    print('\n\n')
    print('*******************International Space Station Data*************************')
    print('\n')
    x = input('Press ENTER to view the current position of the ISS with the people currently on it:')
    print('\n')
    positions = requests.get('http://api.open-notify.org/iss-now.json').json()
    peoples = requests.get("http://api.open-notify.org/astros.json").json()
    # print(response)
    print('Current position of the ISS:')
    print('\n')
    print('Timestamp:' + str(positions['timestamp']))
    print('latitude: ' + positions['iss_position']['latitude'])
    print('longitude: ' + positions['iss_position']['longitude'])
    # print(peoples)
    print('\n')
    print('People currently on the ISS:')
    print('\n')
    x = 0
    for i in peoples['people']:
        x+=1
        print(str(x) + 'st person: ' + i['name'])
        # print()

    print('\n')
    print('Hence at this time there are a total of ' + str(x) + ' people in the ISS.')
    print('\n')
    loop_varri = input('Do you want to continue(y/n):')
    if loop_varri == 'y':
        continue
    else:
        break






