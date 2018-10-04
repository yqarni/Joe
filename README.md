# Joe
Minibot final DE round

#include <kipr/botball.h>

/* arm is port 0 and claw is port 2

Black line = port 0, E.T. = port 5, light = port 3

black line threshold = 2900

ET threshold = 2900 */

void arm_up(); //position 500

void arm_down(); //position 1300

void claw_open(); //position 600

void claw_close(); //position 1300 

void arm_Kdown(); //position 1000

void claw_Kopen();//position 700

void turn_left();

void turn_right();

void black_line();

void short_black_line();

void ET();

void ET_back();

void open_slow();

void close_slow();

int rmotor = 2;

int lmotor = 0;

int main()

{

    //test program

    arm_up();

    claw_close();

    motor(0,70);

    motor(2,70);

    msleep(100);

    ao();

    motor(0,-70);

    motor(2,-70);

    msleep(100);

    ao();

    claw_open();

    arm_down();

    wait_for_light(3);

    shut_down_in(119);

    // msleep(8000);//waiting for create

    //starting position

    arm_down();

    claw_Kopen();



    printf("Hello, my name is Joe Biden. <3 Barack your world/n");

    enable_servos();



    //grab 4 poms on black tape

    arm_up();

    msleep(1000);

    motor(0,70);

    motor(2,70);

    msleep(200);

    ao();

    arm_down();

    claw_close();

    msleep(500);

    set_servo_position(0,200);

    msleep(200);

    set_servo_position(0,400);

    msleep(200);

    set_servo_position(0,500);

    msleep(200);


    //go on ramp

    motor(0,90);

    motor(2,90);

    msleep(2500);

    ao();

    //BEGIN BLACK LINE

    black_line();

    //back up to get beginning poms

    motor(0,-50);

    motor(2,-50);

    msleep(1600);

    ao();

    //get poms

    arm_Kdown();

    msleep(1000);

    claw_open();

    msleep(1000);

    arm_down();

    msleep(1000);

    claw_open();

    msleep(1000);

    printf("WORK!/n");

    //follow rest of black line until ET

    short_black_line();

    printf("Yay black line!/n");

    msleep(1000);

    //Grab poms

    close_slow();

    msleep(1000);

    printf("yay closing!/n");

    set_servo_position(0,1300);

    msleep(500);

    set_servo_position(0,1100);

    msleep(500);

    set_servo_position(0,900);

    msleep(500);

    set_servo_position(0,700);

    msleep(500);

    arm_up();

    msleep(500);



    //FIND ET

    ET();



    //ROUND 1 OF PUTTING THEM IN BIN

    arm_Kdown();

    claw_open();

    msleep(1000);

    claw_close();

    printf("all done/n");

    msleep(1000);

    /////////////////////////

    //ROUND 2 OF GETTING POMS

    ET_back();



    claw_open();

    msleep(500);

    arm_down();

    msleep(1000);

    motor(0,60);

    motor(2,60);

    msleep(200);

    ao();

    close_slow();

    msleep(100);

    motor(0,-60);

    motor(2,-60);

    msleep(500);

    ao();

    arm_up();



    motor(0,60);

    motor(2,60);

    msleep(1500);

    ao();



    //ROUND 2 OF PUTTING POMS IN BIN

    arm_Kdown();

    msleep(1000);

    claw_Kopen();





    //ROUND 3 OF GETTING POMS

    motor(0,-60);

    motor(2,-60);

    msleep(1200);

    ao();



    claw_open();

    msleep(1000);

    arm_down();

    msleep(1000);

    close_slow();

    // claw_close();

    motor(0,-60);

    motor(2,-60);

    msleep(200);

    ao();

    arm_up();



    //ROUND 3 OF PUTTING POMS IN BIN

    motor(0,60);

    motor(2,60);

    msleep(1400);

    ao();



    arm_Kdown();

    msleep(1000);

    claw_open();

    msleep(1000);

    arm_up();

    msleep(1200);

    claw_close();



    //ROUND 4 OF GETTING POMS

    ET_back();



    //GRAB EM

    claw_open();

    msleep(1000);

    arm_down();

    msleep(1000);

    motor(0,60);

    motor(2,60);

    msleep(500);

    ao();

    close_slow();

    motor(0,-60);

    motor(2,-60);

    msleep(200);

    ao();

    arm_up();

    msleep(1000);



    //ROUND 5 OF PUTTING POMS IN BIN

    motor(0,60);

    motor(2,60);

    msleep(1300);

    ao();





    arm_Kdown();

    msleep(1000);

    claw_Kopen();

    msleep(1000);

    arm_up();



    //ROUND 5 OF GETTING POMS



    ET_back();



    //GRAB EM

    claw_open();

    msleep(1000);

    arm_down();

    msleep(1000);

    motor(0,50);

    motor(2,50);

    msleep(500);

    ao();

    msleep(500);

    close_slow();

    msleep(1000);

    claw_close();

    msleep(1000);

    motor(0,-60);

    motor(2,-60);

    msleep(600);

    ao();

    arm_up();



    //ROUND 6 OF PUTTING POMS IN BIN

    ET();



    //drop em

    arm_Kdown();

    msleep(1000);

    claw_Kopen();

    msleep(1000);

    arm_up();







    printf("STAY WOKE/n");

    return 0; 

}



void turn_left()

{

    motor(0, 20);

    motor(2, 65); // Turn arc left.



}

void turn_right() 

{

    motor(0, 65);

    motor(2, 20); // Turn arc right.



}

void claw_open()

{

    set_servo_position(2,500);

    msleep(500);

}

void claw_close()

{

    set_servo_position(2,1300);

    msleep(100);

}

void arm_up()

{

    set_servo_position(0,500);

    msleep(500);

}

void arm_down()

{

    set_servo_position(0,1300);

    msleep(500);

}

void arm_Kdown()

{

    set_servo_position(0,1000);

    msleep(500);

}
void claw_Kopen()
{
    set_servo_position(2,700);
    msleep(500);
}
void black_line()
{
    double start_time = seconds();
    while (seconds() < start_time+16)
    {
        if (analog(0) > 2930)
        {
            turn_right();
        }
        else
        {
            turn_left();
        } 
    }
    ao();
}
void short_black_line()
{
    //double start_time = seconds();
   // while (seconds() < start_time+3)
        while (analog(5) < 2900)
        {
            if (analog(0) > 2930)
            {
                turn_right();
            }
            else
            {
                turn_left();
            } 
        }
    ao();
}
void ET()
{
    // double start_time = seconds();
    // while (analog(5) < 80 && seconds() < start_time+5)
    while (analog(5) < 2900)
    { 
        motor(0, 30);
        motor(2, 30);
    }
    ao();
}
void ET_back()
{
    // double start_time = seconds();
    // while (analog(5) > 1000 && seconds() < start_time+4)
    while (analog(5) > 1180)
    {
        motor(0, -30);
        motor(2, -30);
    }
    ao();
}
void open_slow()
{
    set_servo_position(2,1300);
    msleep(1000);
    set_servo_position(2,1200);
    msleep(1000);
    set_servo_position(2,1100);
    msleep(1000);
    set_servo_position(2,1000);
    msleep(1000);
    set_servo_position(2,900);
    ao();
}
void close_slow()
{
    set_servo_position(2,900);
    msleep(1000);
    set_servo_position(2,1000);
    msleep(1000);
    set_servo_position(2,1100);
    msleep(1000);
    set_servo_position(2,1200);
    msleep(1000);
    set_servo_position(2,1300);
    msleep(1000);
    set_servo_position(2,1400);
    msleep(1000);
    ao();

}
