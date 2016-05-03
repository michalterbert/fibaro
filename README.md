# fibaro
Fibaro virtual devices

## nbox remote control
Pilot do nbox'a Enigma2:
- Działanie oparte o interfejs WWW (OpenWebIF)
- Brak autoryzacji na port 80 dla dekodera

### Przykłady użycia:

#### Kod dla przycisku Power On/Off)
    GET /api/powerstate?newstate=0
    HTTP/1.10x0D0x0A0x0D0x0A

#### Slider dla głośności (Volume +/-), używamy zmiennej `set_sliderValue_`
    GET /web/vol?set=set_sliderValue_
    HTTP/1.10x0D0x0A0x0D0x0A

#### Kody dla przycisków wpisujemy w `XX`:
    GET /api/remotecontrol?command=XX
    HTTP/1.10x0D0x0A0x0D0x0A
  - góra, dół, lewo, prawo (up `103`, down `108`, left `105`, right `106`)
  - ok `352`, exit `174`

#### Kody dla danego kanału TV:
    GET /api/zap?sRef=`XX`
    HTTP/1.10x0D0x0A0x0D0x0A
  - należy do parametru `XX` wpisać kod kanału, najlepiej zrobić to z przeglądarki Chrome i prześledzić jaki odnośnik zostanie uruchomiony po zmianie kanału, u mnie przykładowo jeden z kanałów miał taki kod ``1%3A0%3A1%3A390D%3A32C8%3A13E%3A820000%3A0%3A0%3A0%3``

