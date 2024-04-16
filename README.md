# KSN - Arbeitsauftrag Antonia Dzidzic

##### Thema: FM-Radioempfänger

In meinem GNURadio-Projekt habe ich einen FM-Radioempfänger gebaut, der sich als ziemlich spannend erwiesen hat. Statt eine physische Hardwarequelle zu verwenden, habe ich eine Dateiquelle eingefügt, um das Eingangssignal zu erhalten. Das war mein Ausgangspunkt.

Da die Datei mehrere Radiosignale enthielt, musste ich das gewünschte Signal herausfiltern. Dazu habe ich den "Multiply" Block und die "Signal Source" genutzt. Ich musste sicherstellen, dass das Signal in der Mitte des Spektrums liegt, also habe ich es um +/- 2.5 MHz verschoben.

Um die Signale weiter zu trennen und das gewünschte Radiosignal klar zu empfangen, habe ich einen Tiefpassfilter mit einer Grenzfrequenz von etwa 40 kHz hinzugefügt. Dies war wichtig, um Störungen zu minimieren und das gewünschte Signal zu verstärken.

Nachdem das Signal vorbereitet war, habe ich es über die Soundkarte wiedergegeben, um den Radiosender hören zu können. Es war wirklich aufregend, die Klänge über die Lautsprecher zu hören!

Zuletzt habe ich das Eingangssignal visualisiert, um seine Charakteristiken besser zu verstehen. Hierbei kamen der "frequency sink" und der "waterfall sink" zum Einsatz. Diese Werkzeuge haben mir geholfen, das Spektrum und die Veränderungen im Signal im Laufe der Zeit zu erkennen.

##### Aufbau des FM-Receivers:

Die Blöcke müssen wie in der Abbildung ersichtlich verbunden werden.


##### Erklärungen zu den gewählten Blöcken:

File Source-Block liest die Audiodatei aus der Angabe ein.

Der Multiply-Block multipliziert - Signal Source-Block mit dem File Source-Block, um den Radiosender in die Mitte des Spektrums zu verschieben.

Der Frequency Sink-Block und der Waterfall Sink-Block dienen dazu, die Ausgabe als Spektralanzeige und als Wasserfalldiagramm zu visualisieren.

Der QT GUI Range-Block, dient dazu, die Frequenz beim Signal Source und bei den Sinks zu verändern.

Der Low Pass Filter-Block trennt die Signale.

Der WBFM Receive-Block demoduliert das FM-Signal.

Der Audio Sink-Block dient dazu, die demodulierte Audio abzuspielen!!

##### Konfiguration der Parameter:

Tiefpassfilter: Grenzfrequenz (40 kHz.)

QT GUI Range-Block: Mittenfrequenz (91 MHz) (Start: 88.5M (-2.5M), Stop:93.5M(+2.5M))

Samplerate bei allen Blöcken: 5 MHz








