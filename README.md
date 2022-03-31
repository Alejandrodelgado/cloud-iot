# cloud-iot

## Abstract
Este tutorial está pensado para que te puedas familiarizar con las Posibilidades de Kubernetes - nodered - servicios IoT en IBM CLoud
The idea is be able to execute it, with a Academic initiative account.
It is inspired (or copy, or adapted) from [John Walicki](https://github.com/johnwalicki) Follow him, a person with always interesting ideas!!!

## Technology

- [Kubernetes](https://cloud.ibm.com/docs/containers?topic=containers-getting-started)
- Container registry
- Continous delivery
- [IoT Platform](https://cloud.ibm.com/docs/IoT/index.html)
- Cloudant
- Toolchain

## Steps

### Kubernetes (K8S)

Create a **free** Kubernetes cluster [K8S](https://cloud.ibm.com/kubernetes/catalog/create)
You can do this because when you create the ibm public cloud account you follow the academic Initiative path

<img width="637" alt="image" src="https://user-images.githubusercontent.com/13664652/161129856-121b8bb7-62c7-41bb-aa0e-bb36959f207f.png">

It will take a few minutes, so we will continue...

### IoT Platform

Create IoT Plafrom service (I select FRA)  [IOT-Platform-service](https://cloud.ibm.com/catalog/services/internet-of-things-platform)

<img width="869" alt="image" src="https://user-images.githubusercontent.com/13664652/161130803-ee3c01fd-644b-4e91-a726-90474dd99d67.png">

Once it is created, launch the platform

<img width="1214" alt="image" src="https://user-images.githubusercontent.com/13664652/161131056-fc32b755-6913-4898-b734-4b2ef690aab0.png">

If you have some problems accesing, "login" (the user will appear at top right) and launch it again

<img width="1780" alt="image" src="https://user-images.githubusercontent.com/13664652/161131301-3bde2387-c4f7-480b-a4ee-7bd6a374fe1d.png">

![image](https://user-images.githubusercontent.com/13664652/161131444-7adcb274-05fb-4ae9-be2f-702c34519c44.png)

Now you are ready for create or add a *device*

Lets give it a type and an ID (Android in our lab)

![image](https://user-images.githubusercontent.com/13664652/161131682-a986915d-68d3-4aeb-b28a-78c9d32be5be.png)

In our exercise we will skip the device information *Next*

we will create an authentication token (write down it, you will not be able to recover later) 12345678 in our lab

![image](https://user-images.githubusercontent.com/13664652/161132017-25851975-2ce1-44c0-a12c-3b843382d621.png)

Dont forget to *finish* !!!!

![image](https://user-images.githubusercontent.com/13664652/161132090-dcaea32f-a366-4b0a-9eff-e221f38515e7.png)

It is time to test it.
Download in yor Android [Accelerator app](https://ibm.biz/iot-apk)






