# Troubleshooting Printers 5.6

### Diagnosis

#### Test Page

The printer *Test Page* provided by #windows is useful in determining if your printer is working and properly calibrated. Sometimes the #printer console has its own utilities for troubleshooting and #calibration. 

If you get a *line printed down the entire printed page*, it is time to either **clean your print heads** ( #inkjet) or **inspect the photosensitive drum for scratches** ( #laser) or damage. Sometimes you will need to replace the #photosensitive drum and the #toner cartridge. 

*Faded or blank prints* usually mean you are **low on toner or ink**.

If your *images are doubled* or ‘echoed’, you most likely need to **clean your optical drum**. 

#### Drivers and Language

If your prints *contain unfamiliar characters or languages*, you may have the **wrong** #driver for the model of printer.  Remember that there are **two printing languages**, #PCL and #PostScript – this issue usually occurs when we are **using drivers in the wrong language**.  A bad or **out-of-date installation of an application** can cause these issues as well.  If your printer’s test page is in the wrong language, this is likely to be your issue.

#### Hardware Issues

If you experience *toner smudging*, this is likely a #fuser problem.  The fuser unit is **not heating up or contacting the paper** properly, leaving unfused toner behind.  Replacement of the fuser assembly is usually the needed fix.

*Grinding sounds* from a printer is never a good sign, but hopefully it is a **paper jam**, or the **carriage is misaligned.** If these are not solutions to the grinding, it is possible that the internal mechanisms of your printer are damaged, and you will have to replace the entire unit.

*Finishing Issues* refer to **post-ink applications where the printer will collate the pages** and then either staple the paper set or punch holes through it for binding purposes.  If either of these processes are misaligned, you should verify that it has **current and correct drivers** and install the correct ones if necessary.

##### Paper

If the *paper option you select while printing does not match up with the paper in the printer tray*, an error will occur, and the printer will prompt you to select a different tray or supply the correct paper in the selected tray. 

*Paper jams* are cleared by **firmly grasping the paper and pulling it out** without damaging the internal mechanisms of the printer.  

*Printer misfeeding* is a symptom of **old pickup rollers** that may need to be replaced via laser printer maintenance kit.

*Creased paper* happens when the **paper path is impeded or shifted**, or when the **incorrect weight of paper** is being used.

#### Jobs and Queue

If your print #spooler receives a *corrupted print job*, this can **cause a backup in the print queue that will cause the spooler to enter a feedback loop** where it continues to try to print the corrupted object.  Sometimes **deleting the corrupted job** is all that you need to do to continue printing.

The jobs in the printer queue can be seen in the #logs of either *Windows Event Viewer*, or *Windows Print Service*.

If the **colors on your prints do not match** what you are seeing on your display, you may need to **calibrate your display via a third-party calibration** tool.  Other solutions include calibration of the printer and checking to see if the paper you are using is a factor in the color representation.

If your printer is **not orienting pages by landscape or portrait correctly**, this is likely an issue with a **driver or setting**, check your printers console for further insight.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/troubleshooting-printers-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [052 Troubleshooting Common Hardware Problems](052%20Troubleshooting%20Common%20Hardware%20Problems.md)

#study #professormesser #comptia #Aplus #hardware #driver 