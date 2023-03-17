# Blinking_led_on_CMOD_A7_Artix_7-FPGA
Blinking LED on CMOD A7 Artix-7 35T

Run VIVADO

I am assuming you may have already opened one project , if not then click on create new project

![01](https://user-images.githubusercontent.com/98607828/225977020-ee7f008a-b02f-4dac-9c61-df75a94231d5.jpg)

else
follow the next window if you already opened a project.
1.click on file->New
![1](https://user-images.githubusercontent.com/98607828/225977035-8bc01f1f-c4de-49f2-b3a6-65266a00466d.jpg)

  
2. click Next
 ![2](https://user-images.githubusercontent.com/98607828/225977298-ea52197a-dfb6-46d0-992c-9549622328e8.jpg)

 
3. Give an appropriate name to the project so you can remember, and also the location where you can come back and add more files.
![3](https://user-images.githubusercontent.com/98607828/225977345-63a67884-c7b1-4bd2-afb5-f1a241969294.jpg)

4 . click Next
![4](https://user-images.githubusercontent.com/98607828/225977417-6d778de9-311c-4866-af79-9c63bc4745a3.jpg)

5.Select the family name , Package and speed grade as accordingly.
![5](https://user-images.githubusercontent.com/98607828/225977518-2b7ee665-7553-47ab-9645-1ae96ed8c3b4.jpg)



6.click finish
![6](https://user-images.githubusercontent.com/98607828/225977683-15026cde-c50d-4228-aeec-843d7e063246.jpg)


7. Click Next

![7](https://user-images.githubusercontent.com/98607828/225977785-b9cc5851-acb7-4372-a60a-b6a6ade30226.jpg)

8.Give a name to Verilog HDL file. You can also choose VHDL/System Verilog but for that you have to write hdl code in those languages.
  ![8](https://user-images.githubusercontent.com/98607828/225977844-414071bd-7da6-4028-9861-60dcffc0eafd.jpg)


9. Select the family name , Package and speed grade as accordingly.

![9](https://user-images.githubusercontent.com/98607828/225977921-52b4d8ed-d6a7-41b4-a524-975393c4a346.jpg)


10.Click Ok.
![10](https://user-images.githubusercontent.com/98607828/225977973-47e30343-a0f1-42ed-9ccd-587fbf125da1.jpg)

11. Click Finish.

![11](https://user-images.githubusercontent.com/98607828/225978089-88201c90-f41e-4f3d-8828-2aff822797aa.jpg)


12.Here's the simple led blink code for CMOD A7 ARTIX-35T FPGA

  ![12](https://user-images.githubusercontent.com/98607828/225978153-38b24f94-4504-42cf-b36a-a482df28d46b.jpg)




13. Now, click on (+) in source tab and choose add or create design sources.


![13](https://user-images.githubusercontent.com/98607828/225978361-8f9bd540-61ae-4c08-8610-e60512f45498.jpg)


14. after giving a name to xdc file , copy the constraints file from here -:
Digilent/digilent-xdc: A collection of Master XDC files for Digilent FPGA and Zynq boards. (github.com)
for CMOD A7 ARTIX_35T FPGA BOARD
Since this FPGA uses 12MHZ,so we're dividing this frequency by half to run the led at 1HZ(1second) rate.
Mention the i_clk (which is the input clock in our TOP Design) into xdc file .
similarly , mention the led(output from TOP Design) in XDC file in ##LED section.
Now we're done ..

![14](https://user-images.githubusercontent.com/98607828/225978408-c9840f8e-0dba-4c01-9f62-d2785d15e46c.jpg)


15. now we're done with basic flow about writing HDL and adding constraints.
since this is just a basic blinky test on FPGA, so we're assuming the RTL code we've written would work correcly, for that we don't have to simulate this as it would take about 6_000_000 clk cycles to get signal going as high and again next 6_000_000 clk cycles to go low.
Anyways, I would definitely show you, how it looks like, because waveforms are sort of heart of FPGA design signals. 😀
Now, as we added design file, similarly we 'll add simulation file.

 ![15](https://user-images.githubusercontent.com/98607828/225978515-5cebd709-c174-4a92-95dc-0616be13afab.jpg)
 
 here's how typical led blinky testbench look like in Verilog
Quite easy, right?
click on Run Simulation in Project Manager - Run as Behavioral Simulation.

![sim](https://user-images.githubusercontent.com/98607828/225978810-780e9210-8bfd-4141-bb2e-f6c6064103d7.jpg)


![sim_2](https://user-images.githubusercontent.com/98607828/225978790-ae898dbe-f74c-4203-9342-15c5fed21294.jpg)

![sim_3](https://user-images.githubusercontent.com/98607828/225978823-9421de1e-0bd3-453b-b492-5d7c5c6e504f.jpg)

![sim_4](https://user-images.githubusercontent.com/98607828/225978858-661d9bfb-c5db-4be2-8856-4d4fcbbf456b.jpg)


16.Now as we have also simulated and check the functional verification of our logic design, now next flow is pretty easy, just click on Generate Bitstream in Project manager as it would ask you about running synthesis, before implementation, you should accept it by clicking as yes.


![16](https://user-images.githubusercontent.com/98607828/225978954-d3a46b94-1773-4668-a75d-244b170555ec.jpg)



17.  Click on Open Hardware Manager on above pop-up window, otherwise, go to project manager window, click on open Hardware Manager, just down to Generate bitstream in PROGRAM AND DEBUG Section.
Make sure while programming FPGA , you have got it connected with your Laptop/PC, after locating bitsream file (which is generated by VIVADO tool) in your project location, click on program - program device.



![16](https://user-images.githubusercontent.com/98607828/225979779-f0a608cc-2209-44ba-9da7-6be304c8ea5a.jpg)

18. DEMO
led blink test successfullThat's it, folks, now I hope you would be able to do basic FPGA design from scratch...
   
![My Video](https://user-images.githubusercontent.com/98607828/225979984-65ded42a-8dc9-4904-bf22-6f9115df8694.gif)




