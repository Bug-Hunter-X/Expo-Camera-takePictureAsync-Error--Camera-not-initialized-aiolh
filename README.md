# Expo Camera takePictureAsync Error: Camera not initialized

This repository demonstrates a common error encountered when using the Expo Camera API: calling `takePictureAsync` before the camera is fully initialized.  The provided solution ensures the camera is ready before taking a picture.

## Problem

The `takePictureAsync` method of the Expo Camera API might throw an error if called too early in the component's lifecycle.  This often results in an error message indicating the camera isn't ready.

## Solution

The solution involves checking the camera's status using the `cameraRef.current.getStatusAsync()` method.  This method returns an object containing the camera's status, including whether it's ready.  We wait for the camera to be ready before attempting to take a picture. This is demonstrated using `async/await`.