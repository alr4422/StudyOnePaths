
int radius;
int length;
int[] res = new int[2];

void setup() {
  // Create a 640x400 pixel canvas
  size(640, 400);
  // use a black background.
  background(0);
  // use white for drawings points.
  stroke(255);
  // call the draw curve function starting on position 200,300
  radius = 100; // radius is 100 pixels
  
  res = draw_curve(200,200,radius);
}

// Now we want a function that draws an arc. The function takes as input the
// starting coordinates, it returns the end coordinates, and it draw a curve inside.
int[] draw_curve(int initial_x, int initial_y, int radius) {
  //stroke(130);
  //point(current_x,current_y);
  //stroke(255);
        int current_x = initial_x;
        float current_y = initial_y;
        for (int i=0; i<2*radius; i+=1){
                current_x+=1;
                current_y=initial_y+sqrt(pow(radius,2)-pow(i,2))-radius;
                point(current_x, current_y);
        }
        int[] finalposition = new int[2];
        finalposition[0] = current_x;
        finalposition[1] = int(current_y);
        return finalposition;
}

