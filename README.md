let rectangles = [];

function setup() {
  createCanvas(400, 400);
for (let i = 0; i < 10; i++) {
    let rectObj = {
      x: random(width), 
      y: random(height), 
      width: random(40, 80), 
      height: random(20, 60),
      speed: random(1, 3),
      color: color(random(255), random(255), random(255))
}
       rectangles[rectangles.length] = rectObj;
  }
}
  function draw() {
    background(220);
    for (let i = 0; i < rectangles.length; i++) {
        let r = rectangles[i];
        if (mouseX > width / 2) {
          r.speed = 5; 
        } else {
          r.speed = random(1, 3); 
        }
   
    r.width += 0.1; // Slowly increase the width
    r.height += 0.05; // Slowly increase the height
    r.y += r.speed;
    if (r.y > height) {
      r.y = -r.height;
    }
    fill(r.color);
    rect(r.x, r.y, r.width, r.height);
  }
}
