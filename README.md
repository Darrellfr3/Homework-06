# Weather Dashboard

## Introduction

> This program is intended to return current and forecast weather conditions of whichever city the user submits into the input. Currently, it is still a work in progress as a recent search history and the forecast elements of the program haven't been fully implemented.

## Snapshot

(/Assets/mock.png)

## Code Samples

a snippet of the function that fills the current weather conditions of the city user submitted.

    function currentWeather(){
            var cityEl=$("#city").val().trim();
            var queryURL="https://api.openweathermap.org/data/2.5/weather?        
            q="+cityEl+"&units=imperial&appid=a2e4f9a95bb5b2a32ad28b367f752e70";

            $ajax({url:queryURL,method:"GET"}).then(function(response){
               var lonEl=response.coord.lon;
               var latEl=response.coord.lat;

               $("#currentTemp").text((response.main.temp).toFixed(1)+"°F");
               $("#currentHumid").text(response.main.humidity+"%");
               $("#currentWind").text((response.wind.speed).toFixed(1)+" MPH");

## Installation

> Usage of this program is done by entering the name of the city you wish to search then press the submit button. After the search history feature is implemented then the user will be able to click buttons on the aside underneath the search bar that brings back past information based on the city clicked.