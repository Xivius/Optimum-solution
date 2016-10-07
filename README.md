# Optimum-solution
ECE 100 Team 1
void veerRight(){
    motor(leftMotor, 100);
    motor(rightMotor, 0);
}

void veerLeft(){
    motor(rightMotor, 100);
    motor(leftMotor,0);
}

void main(){
    
    int leftMotor=0;
    int rightMotor=3;
    int leftEye = 2;
    int rightEye = 6;		//changed rightEye = 3 to 6; maybe that is why HandyBug was getting confused. Both Right motor and Right Eye were set to 3.
    int onTape=50;
    int counter = 1;
    
    while(1){
        
        if(analog(rightEye) <= onTape && analog(leftEye) >= onTape){
            veerRight();
            sleep(.02);
            counter = 1;
        }
        else if(analog(leftEye) < onTape && analog(rightEye) > onTape){
            veerLeft();
            sleep(.02);
            counter = 0;
        }
        else{
            if(counter = 1){
                veerRight();
                sleep(.02);
            //    counter = 1;					The reason this is commented out is because it seems redundant 
            }
            if(counter = 0){
                veerLeft();
                sleep(.02);
            //   counter = 0;					The reason this is commented out is because it seems redundant 
            }
        }    
    }
}
