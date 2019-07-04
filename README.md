<h2><b>Widget zur Anzeige von SMAPortal-Daten im FHEM Tablet UI</b></h2>

Dieses Widget ist für den Einsatz von FHEM Tablet UI 2.x vorgesehen.
Voraussetzung ist das Vorhandensein von SMAPortal-Grafikdevices.
Grafikdevices werden im existierenden SMAPortal FHEM-Device angelegt 
mit:

     set <SMAPortal-Device> createPortalGraphic <Typ>
  
Das entstandene Device ist im Attribut "data-device" des Widgets einzutragen.



<b>Installation</b>

Die Datei widget_smaportalspg.js muss in das js Verzeichnis der fhem-tablet-ui installation und 
die Datei ftui_smaportalspg.css in das entsprechende css-Verzeichnis.

In FHEM kann dazu der Befehl:

     update all https://raw.githubusercontent.com/nasseeder1/fhem-ftui_smaportalspg_widget/master/controls_smaportalspg_widget.txt
     
verwendet werden um die Dateien einmalig zu installieren. Sollen die DAteien in den regelmäßigen update-Prozess mit eingebunden werden, kann das control-File in FHEM integriert werden:

     update add https://raw.githubusercontent.com/nasseeder1/fhem-ftui_smaportalspg_widget/master/controls_smaportalspg_widget.txt

<b>Attribute des smaportalspg-Widgets</b>

	data-device 		SMAPortal-Graphicdevice in FHEM, dessen Inhalt angezeigt werden soll 		
	data-get 		Name des Readings, das eine Änderung des SMAPortalSPG-Devices anzeigt 	
	                        default: 'parentState' 	
	data-max-update 	Maximale Häufigkeit in Sekunden für das Update des SMAPortalSPG-Devices	
	                        default: '2'

<b>Beispiel</b>
      
        <li data-row="1" data-col="1" data-sizey="3" data-sizex="4">
         <header>SMA Grafik</header>
           <div class="cell">
             <div data-type="smaportalspg" data-device="SPG1.Sonnenstrom" data-get="parentState" ></div> 
          </div>
	    </li>   


<b>Hinweis:</b> Es ist immer ein Grafik-Device in FHEM mit SMAPortal zu erstellen und im Attribut "data-device" 
anzugeben, nicht das SMAPortal-Device selbst !
