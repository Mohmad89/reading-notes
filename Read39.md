# Get the last known Location

* Using Google Play Services location APIs we can get the location.

## 1. Set Up Google Play Services

1. Download and install the Google Play Services Component via the SDK Manager 
2. Add the library to your project.

## 2. Specify App Permissions

## 3. Create Location Services Client

* In your activity's onCreate() method, create an instance of the Fused Location Provider Client as the following code snippet shows.
    - fusedLocationClient = LocationServices.getFusedLocationProviderClient(this);

## 4. Get The Last Known Location

* with use getLastLocation() method 
    - fusedLocationClient.getLastLocation()
        .addOnSuccessListener(this, new OnSuccessListener<Location>() {}
* the the getLastLocation() method tack us null in this situations : 
    - Location is turned off in the device settings.
    - The devixe never recorded its location.
    - Google Play Services on the device has restarted.

## 5. Choose The Best Location Estimate 

* The FusedLocationProviderClient provides several methods to retrieve device location information.
    - getLastLocation() : gets a location estimate more quickly and minimizes battery usage that can be attributed to your app.
    - getCurrentLocation() gets a fresher, more accurate location more consistently. However, this method can cause active location computation to occur on the device.