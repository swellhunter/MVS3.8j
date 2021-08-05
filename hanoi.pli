//HERCMMPH JOB (PL1),'PL1 Hanoi',CLASS=A,MSGCLASS=C,
//             REGION=8M,TIME=5,MSGLEVEL=(2,1),NOTIFY=HERCMM
//********************************************************************
//* Name: HERCMM.PDS.PL1(HANOI)
//* Desc: Towers of Hanoi adapted from IronSpring PL/I demo program.
//********************************************************************
//PROGPL1   EXEC PL1LFCG,PARM.PL1L='LOAD,NODECK,OPT=02,NEST'
//PL1L.SYSLIN DD UNIT=SYSDA
//PL1L.SYSIN  DD *
 /* HANOI                                                 */
 /*********************************************************/
 /*                                                       */
 /* MODULE:   HANOI                                       */
 /*           AUTHOR UNKNOWN, TAKEN FROM IRONSPRING DEMO. */
 /*                                                       */
 /* FUNCTION: 'TOWERS OF HANOI' PROBLEM.                  */
 /*                                                       */
 /* USAGE:    HANOI                                       */
 /*                                                       */
 /* DEPENDENCIES:                                         */
 /*           NONE                                        */
 /*                                                       */
 /*********************************************************/
 HANOI: PROCEDURE OPTIONS(MAIN);

    DECLARE(DISK, FROM, TO, TEMP) FIXED BINARY(31);
    DISK = 3; FROM = 1; TO = 3; TEMP = 2;

    CALL DO_HANOI(DISK, FROM, TO, TEMP);

    DO_HANOI: PROCEDURE(DISK, FROM, TO, TEMP) RECURSIVE;
       DECLARE(DISK, FROM, TO, TEMP) FIXED BINARY(31);

       IF DISK > 0 THEN
          DO;
             CALL DO_HANOI((DISK - 1), FROM, TEMP, TO);
             CALL MOVE_DISK(FROM, TO);
             CALL DO_HANOI((DISK - 1), TEMP, TO, FROM);
          END;

    END DO_HANOI;

    MOVE_DISK: PROCEDURE(FROM, TO);
       DECLARE (FROM, TO) FIXED BINARY(31);
       PUT SKIP FILE(SYSPRINT) LIST('MOVE' || FROM, '->' || TO);
    END MOVE_DISK;

 END HANOI;
/*
//GO.SYSPRINT DD SYSOUT=*,DCB=(RECFM=FBA,LRECL=133,BLKSIZE=26600)
//GO.SYSIN    DD DUMMY
