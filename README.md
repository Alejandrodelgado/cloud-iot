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

You would need some data
<img width="347" alt="image" src="https://user-images.githubusercontent.com/13664652/161154552-e77a175c-5e55-4138-ba59-369a60025a7b.png">

At top right you have the organization that need in the aplication
The device name "Android"
The code "12345678"

Now the device appears as connected

<img width="1051" alt="image" src="https://user-images.githubusercontent.com/13664652/161155260-2e7b5bb4-ad87-4369-8ca1-f48d2c1e0eb8.png">

And you will start receiving events

<img width="818" alt="image" src="https://user-images.githubusercontent.com/13664652/161155325-2c787882-22bd-4071-9424-52af0f9e07c7.png">

and events are like this
{
	"d": {
		"acceleration_x": 0.2681506,
		"acceleration_y": 0.038307227,
		"acceleration_z": 9.730036,
		"roll": -0.027552081,
		"pitch": -0.003935493,
		"yaw": 0.0030526258,
		"longitude": 0,
		"latitude": 0,
		"heading": 0,
		"speed": 0,
		"trip_id": "1648763355",
		"timestamp": "2022-03-31T23:51:36.404+02:00"
	}
}

<img width="491" alt="image" src="https://user-images.githubusercontent.com/13664652/161155471-4eca0222-c339-46bc-baf1-6ed90fa85a9a.png">


### Node Red

It is time now to create a nodered application that will allow us to move data from an environment to other, in this lab to visualize.

Browse in the [catalog](cloud.ibm.com/catalog)  Node red or use this [link](https://cloud.ibm.com/developer/appservice/create-app?starterKit=59c9d5bd-4d31-3611-897a-f94eea80dc9f)

<img width="920" alt="image" src="https://user-images.githubusercontent.com/13664652/161156266-62c36579-6f1d-44a3-9f62-de3afe9b23a3.png">

<img width="730" alt="image" src="https://user-images.githubusercontent.com/13664652/161156466-f381fcdd-f2d1-4ab7-b3a4-3baccbc7a00d.png">

After a few seconds it will be ready
<img width="1070" alt="image" src="https://user-images.githubusercontent.com/13664652/161156550-f590c527-7e93-4cba-b7c3-198fa8f188f1.png">

Now click on deploy

<img width="855" alt="image" src="https://user-images.githubusercontent.com/13664652/161156742-cbd60f2a-ebd8-4d3c-a55f-b223ea8e410d.png">

Select Kubernetes as deploy
Create an API Key (just click in the button NEW)
Select Frankfurt as region for deploy.

You will be request to configure the toolchain (select also FRA)

<img width="494" alt="image" src="https://user-images.githubusercontent.com/13664652/161156959-c31eba93-6bf0-427f-8437-8aea5b377c00.png">

You will be returned to the previous page and you will see the progress.

<img width="1134" alt="image" src="https://user-images.githubusercontent.com/13664652/161157093-51dde111-6f0b-4fc5-b966-508945f0bb10.png">

If you reload the page, some changes appears

<img width="443" alt="image" src="https://user-images.githubusercontent.com/13664652/161157189-57cfe1f9-da66-4c4e-b3f5-994bd91ad363.png">

It will take about 5-10 min to deploy, you can use this time to explore the pipelines

As it finish, the app url is filled

<img width="1145" alt="image" src="https://user-images.githubusercontent.com/13664652/161158857-e64a1c11-4f07-40df-8774-0ff331dd949f.png">

You can click in it to access nodered

<img width="973" alt="image" src="https://user-images.githubusercontent.com/13664652/161158899-785a4367-6e46-45fa-9f6c-af4c3adaa12b.png">

To start working with it, just next  next - next.
In order to execute the labs, i would recommend leave it Unsecure. Just in order to avoid problems during the labs, not for production.

<img width="801" alt="image" src="https://user-images.githubusercontent.com/13664652/161159012-e35d8a59-1514-43ac-adb8-579a5be07d76.png">

<img width="1077" alt="image" src="https://user-images.githubusercontent.com/13664652/161159050-3a9d480d-8101-44d7-abdc-dbdb66fb8705.png">

Click on GOTO your NODERED

<img width="1077" alt="image" src="https://user-images.githubusercontent.com/13664652/161159089-277bddd8-6c09-4a82-bd88-caf1e4c19244.png">

Here we are

<img width="1176" alt="image" src="https://user-images.githubusercontent.com/13664652/161159171-eb25fb6b-9ba8-4902-a4cd-144765e91e07.png">

Click on the small bug on the right-top and in the button close to the "hello" tab

<img width="1176" alt="image" src="https://user-images.githubusercontent.com/13664652/161159274-4d9b9a01-a906-43c9-aaac-444e5e39fd80.png">

<img width="1030" alt="image" src="https://user-images.githubusercontent.com/13664652/161159312-5e00b44b-d5ff-4166-911c-fd8a01b7a2fe.png">


Now it is time to include a couple of "palettes"

node-red-contrib-scx-ibmiotapp
node-red-dashboard

at top right - manage palette

<img width="411" alt="image" src="https://user-images.githubusercontent.com/13664652/161159414-78519687-443c-4b1e-812f-250c6bd1129a.png">

and now install it

<img width="739" alt="image" src="https://user-images.githubusercontent.com/13664652/161159477-0f75715d-7d83-40dd-971a-1d0e569bff40.png">

<img width="696" alt="image" src="https://user-images.githubusercontent.com/13664652/161159563-6c435db3-621e-4131-840d-a936c0a733e9.png">

<img width="462" alt="image" src="https://user-images.githubusercontent.com/13664652/161159593-86e52dc3-513e-4779-a9ac-f7db20314c35.png">

This is what we are going to build

![image](https://user-images.githubusercontent.com/13664652/161166022-2a4507a1-70b2-4f78-8ce7-d1096434e6c9.png)

Now in the top left, type iot in the search 

<img width="557" alt="image" src="https://user-images.githubusercontent.com/13664652/161159697-33218d04-b4c3-4196-b299-0b7a1aaf82c9.png">

drag and drop in the flow, and click in it

![image](https://user-images.githubusercontent.com/13664652/161159820-7d680cb9-d0f1-485b-a48d-468a946cfa06.png)

Select api key in authentication and clik in the pencil at the right of api key

![image](https://user-images.githubusercontent.com/13664652/161159888-627d1eea-f3e6-4747-a639-dad96778d396.png)

We will need gather all this values from the IoT Plaform, in the Apps label

<img width="248" alt="image" src="https://user-images.githubusercontent.com/13664652/161165360-d3732f7e-a18a-4541-8053-28de33c54b1b.png">

Click on generate API Key

<img width="908" alt="image" src="https://user-images.githubusercontent.com/13664652/161165444-38db1e5a-8f5a-4364-88bc-cdccfdb2a8ff.png">

Choose Device Application and click on generate key

<img width="856" alt="image" src="https://user-images.githubusercontent.com/13664652/161165484-bb304510-d22a-4133-98f6-ea47ea09b54d.png">

And here you have both Api Key and token.
Be care as you would not be able to recover it later, copy it.

<img width="714" alt="image" src="https://user-images.githubusercontent.com/13664652/161165600-72dc5f3d-634b-48e8-a088-41ee4007abf2.png">

Now add a function node and include this code (for the X value)

msg.payload=msg.payload.d.acceleration_x;
msg.topic="X-Axis";
return msg;

![image](https://user-images.githubusercontent.com/13664652/161165847-e6bca777-132f-41d7-8e8f-b43c447e3cb5.png)

and do the same for Y and Z

msg.payload=msg.payload.d.acceleration_y;
msg.topic="y-Axis";
return msg;

msg.payload=msg.payload.d.acceleration_z;
msg.topic="z-Axis";
return msg;

and just to finish we will add the chart node

<img width="1039" alt="image" src="https://user-images.githubusercontent.com/13664652/161166442-1266101b-b396-4abf-81a8-3a6e52a781ef.png">

We need add a dashboard group (just click add and done)
select the kind of graph that could help, for instance radar

<img width="516" alt="image" src="https://user-images.githubusercontent.com/13664652/161166492-7879ed8e-eecb-4f73-b151-7cf954e4d535.png">

and use a url like this (the ip and the port of node red slash "ui"

9.51.206.182:31696/ui

<img width="368" alt="image" src="https://user-images.githubusercontent.com/13664652/161166801-3d2658fb-8448-4f1a-88ef-d4584545f31a.png">







