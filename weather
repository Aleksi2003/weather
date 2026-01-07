<?php
// Kaupunki ja oma API-avain
$city = "Helsinki"; // Voit muuttaa esimerkiksi "Tampere"
$apiKey = "e4bf0f064eea86686c444b943c64e936"; // Lisää oma OpenWeatherMap API-avain tähän

// API-osoite
$url = "http://api.openweathermap.org/data/2.5/weather?q=$city&appid=$apiKey";

// Hae JSON-data
$response = file_get_contents($url);

// Tarkista, että haku onnistui
if ($response === FALSE) {
    die('Virhe haettaessa dataa.');
}

// Jäsennä (decode) JSON-data taulukoksi
$data = json_decode($response, true);

// Tulosta halutut tiedot
if (isset($data['main'])) {
    echo "<h2>Sää kaupungissa $city</h2>";
    echo "Lämpötila: " . round($data['main']['temp'] - 273.15, 1) . " °C<br>"; // Kelvin → Celsius
    echo "Kosteus: " . $data['main']['humidity'] . "%<br>";
    echo "Ilmanpaine: " . $data['main']['pressure'] . " hPa<br>";
    echo "Sääkuvaus: " . $data['weather'][0]['description'] . "<br>";
} else {
    echo "Tietoja ei löytynyt.";
}
?>
