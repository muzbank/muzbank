Muzbank 
=======


This is code of Map Yandex with setup at json format:


h2>Scheme/h2
div class="content"
script src="http://api-maps.yandex.ru/2.0/?load=package.standard&amp;lang=ru-RU" type="text/javascript" /script
script type="text/javascript"
var myMap;
ymaps.ready(init);
function init()
{
    ymaps.geocode('52.307799,52.307799', {
        results: 1
    }).then
    (
        function (res) 
        {
            var firstGeoObject = res.geoObjects.get(0),        
                myMap = new ymaps.Map 
                ("map",
                    {
                        center: firstGeoObject.geometry.getCoordinates(),
                        zoom: 16
                    }
                );
            var myPlacemark = new ymaps.Placemark 
            (
                firstGeoObject.geometry.getCoordinates(),
                {
                    iconContent: 'City, &quot;Region&quot;',
  				hintContent: 'name &quot;Уют&quot;,  &quot;Subname&quot;'
                },
                {
                    preset: 'twirl#redStretchyIcon' 
                }
            );
            myMap.geoObjects
            .add(myPlacemark);
            myMap.controls
            .add('zoomControl', {
                left: 1,top: 1     
				})   
            .add('typeSelector'); 
        },
        function (err)
        {
            alert(err.message); 
        }
    );
}
/script
div id="map" style="width: 650px; height: 550px;"  /div
/div





This is URL of Muzbank

http://muzbank.net/

