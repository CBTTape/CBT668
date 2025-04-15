# CBT668
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 668 is from Hunter Guanghui Zhou, and contains a program  *   FILE 668
//*           to offload JES2 spool to separate datasets on your    *   FILE 668
//*           system.                                               *   FILE 668
//*                                                                 *   FILE 668
//*      Program    : OFFLOAD                                       *   FILE 668
//*      Description: JES Spool Offload Program.                    *   FILE 668
//*      Purpose    : Offload JES Spool Data to cataloged           *   FILE 668
//*                   dataset.                                      *   FILE 668
//*      Design     : Hunter Guanghui Zhou                          *   FILE 668
//*      Support    : Phone: 1-(416)-602-9567                       *   FILE 668
//*                   E-mail: zhough2000@yahoo.com                  *   FILE 668
//*                                                                 *   FILE 668
//*      Last Update: February, 2004                                *   FILE 668
//*                                                                 *   FILE 668
//*      I have created a package OFFLOAD to offload JES spool      *   FILE 668
//*      job output to dataset level using SAPI.  It is used to     *   FILE 668
//*      offload the joblog in our environment.                     *   FILE 668
//*                                                                 *   FILE 668
//*      The features are:                                          *   FILE 668
//*      1. The program can offload the spool data in JES OUTPUT    *   FILE 668
//*          queue into system catalogued datasets as following     *   FILE 668
//*          format:  hlq.jobname.Ddate.jobid.TtimeIid              *   FILE 668
//*                                                                 *   FILE 668
//*      2. The spool data selection criteria can be given in       *   FILE 668
//*         EXEC PARM, which includes:                              *   FILE 668
//*                                                                 *   FILE 668
//*          * one or more output classes, maximum 36 classes       *   FILE 668
//*          * Submit USERID, support wildcards (* and ?)           *   FILE 668
//*          * Jobname, support wildcards (* and ?)                 *   FILE 668
//*          * Output destination, support wildcards (* and ?)      *   FILE 668
//*          * Output form, support wildcards (* and ?)             *   FILE 668
//*                                                                 *   FILE 668
//*      3. Output dataset features:                                *   FILE 668
//*                                                                 *   FILE 668
//*          * Use VBA to remove trailing spaces, in order to       *   FILE 668
//*            save disk space.                                     *   FILE 668
//*          * Add message JOF700I at the beginning of each         *   FILE 668
//*            offloaded DD, in order to separate the DDs in job    *   FILE 668
//*            log.                                                 *   FILE 668
//*          * Use higher level qualifier at the execution time,    *   FILE 668
//*            more flexible for different usage.                   *   FILE 668
//*          * Spool data is offloaded when it's ready to           *   FILE 668
//*            offload in JES spool.                                *   FILE 668
//*                                                                 *   FILE 668
//*      4. Operation features:                                     *   FILE 668
//*                                                                 *   FILE 668
//*          * Provide logs in SYSPRINT DD with more meaningful     *   FILE 668
//*            information.                                         *   FILE 668
//*          * Support MVS system command STOP to stop the task.    *   FILE 668
//*            When the program is started in JCL batch, it must    *   FILE 668
//*            be stopped by MVS STOP command.                      *   FILE 668
//*                                                                 *   FILE 668
//*      For example, PARM='H=LG.JOBLOG,C=8,J=@*' means offload     *   FILE 668
//*      all spool data with output class 8 and job name started    *   FILE 668
//*      with @, the output dataset HLQ is 'LG.JOBLOG'              *   FILE 668
//*                                                                 *   FILE 668
//* >>>> Note:  In z/OS 2.1, the macro IAZSSS2 has changed, in that *   FILE 668
//*             its "version number default" is now "3" instead     *   FILE 668
//*             of "2".  This is field SSS2CVER, which now defaults *   FILE 668
//*             to "3".  The local fix is to change SSS2CVER in     *   FILE 668
//*             the OFFLOAD source to SSS2VCTP, which is always     *   FILE 668
//*             equal to "2", and we no longer use the default      *   FILE 668
//*             version number.  Problem symptom was error message: *   FILE 668
//*                                                                 *   FILE 668
//*      IGD17101I DATA SET ????????.????????.DATASET               *   FILE 668
//*      NOT DEFINED BECAUSE DUPLICATE NAME EXISTS IN CATALOG       *   FILE 668
//*      RETURN CODE IS 8 REASON CODE IS 38 IGG0CLEH                *   FILE 668
//*                                                                 *   FILE 668
//*      (Courtesy of Ed Tobias:  tobiaet@dshs.wa.gov  )            *   FILE 668
//*                                                                 *   FILE 668
```
