## MECA 482 Ball on Plate 
Presented by Group 3: Carlos Villasenor,
Brandon Briseno,
Grant Patterson,
Katherynne Estrada,
Pachia Vang
 

## Table of Contents 
 1. Introduction
 2. Capabilities Database 
 3. Operational Viewpoint 
 4. Logical/Functional Viewpoint 
 5. Mathematical Model of the System 
 6. Design
 7. Stimulation 


## 1. Introduction 
Control system theories are applied to many applications to help improve productivity and enhance today’s technology. This report will display the importance and necessary components of control system design through mathematical and simulation modeling. The goal of the project is to develop a comprehensive solution to control a ball’s position on a self-stabilizing flat plate. The ball on plate system consists of a plate that will be tilted using two servo motors to control the plate across the x and y directions as well as a camera to act as a sensor. The models provided in this report will not include the sensor. All models and controls are based off of the operational viewpoint.

## 2. Capabilities Database
The design is simple but effective.
The camera works as a sensor to detect the position of the ball
The rotary servos will be connected to the plate allowing for movement of the plate in all directions.
The main support beam, which is stationary, provides support to the platform to ensure a leveled base.
The servos will be attached to the base and slightly under the plate to keep the design compact as well as aid in sufficient support for the platform assembly. 

## 3. Operational Viewpoint 
![Opertional Viewpoint](https://user-images.githubusercontent.com/35712413/144789129-284a001f-f0cc-4ce9-9b9b-4296c430aad4.jpg)

## 4. Logical/Functional Viewpoint 
![Logical_Functional Viewpoint](https://user-images.githubusercontent.com/35712413/144789135-3cbc3698-73db-405e-968a-6798f5b5117d.jpg)

## 5. Mathematical Model of the System 
The free body diagram of our system is the following: 
![Free Body Diagram](https://user-images.githubusercontent.com/35712413/146634759-ef89ca2f-2c76-4e8e-9ba9-480f7d11f069.jpg)

The following is assumed of the system:
The ball is not slipping.
The ball is perfectly symmetrical and smooth. 
All friction is neglected. 
The ball and plate are in contact with each other at all times

After the anaylsis which can be found in our report, the transfer function was found to be:  
![transfer function](https://user-images.githubusercontent.com/35712413/146634880-bc643f6d-3fa2-48f9-b059-da4296a98603.JPG)

## 6. Design 
- Simulink/MatLab: 

The approach taken to create the Simulink model was utilizing the PID controller block. Following the method used in the provided PID videos, the Control System Designer application within Simulink includes a root locus editor that allows the user to manually move the poles and zeros to obtain the desired PID gains.  Using the root locus editor and a step response graph, it was possible to obtain a critically damped situation. The tool utilized can be found in Appendix C of the report. Below displays the Simulink deisgn and the step reponse of th root locus editor. 

![PID](https://user-images.githubusercontent.com/35712413/146652809-41757709-f5c9-40b0-a0fc-0da82e579db1.JPG)
![step response](https://user-images.githubusercontent.com/35712413/146652804-41bb9f63-abd6-427c-9190-2a672497eee7.JPG)

- Coppelia 

The CoppeliaSim model consists of basic geometries such as rectangular prisms, cuboids,and cylinders. The purple cylinders are intended to simulate a motor that controls the yellow rectangular prisms that act as beams connected to the plate. In order to allow for movement a series of joints was utilized. The black center rod has a prismatic joint and a spherical joint towards the top to allow for translation . The motors have rectangular prisms attached to them that serve as arms that then connect to the yellow beams that hold the plate. The motor implementation was done by adding two joints. The first, is a revolute joint that is placed in the center of the motor. The next one, is another revolute joint that connects the motor arm to the beam. A camera vision code was then implemented and allows the camera to sense the position of the ball and send input signals to the motors to adjust their rotation until equilibrium is met. The figure below depicts the model in CoppeliaSim, of the ball and plate system while Appendix B-1 contains code for the CoppeliaSim model. 

![Coppelia](https://user-images.githubusercontent.com/35712413/146652838-aa945454-eb0e-4fcd-badc-0e99533b83e7.JPG)

## 7. Stimulation 
If video is not working, the stimulation video can be found in the files as "Simulation Video(1)"
https://user-images.githubusercontent.com/35712413/146652613-fa2a2308-1411-4fa7-935b-141fd503ad90.mp4



