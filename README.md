# Project-B
#  Controlled bridge rectifier with Arduino
 // Controlled bridge rectifier with Arduino 
#define scr1_gate   8 
#define scr2_gate   9 
#define pot        
A0 
byte ZC = 0; 
uint16_t alpha; 
void setup(void) { 
pinMode(scr1_gate, OUTPUT); 
digitalWrite(scr1_gate, LOW); 
pinMode(scr2_gate, OUTPUT); 
digitalWrite(scr2_gate, LOW); 
attachInterrupt(0, ZC_detect, CHANGE);       
} 
void ZC_detect() { 
if(digitalRead(2)) 
ZC = 1; 
else 
ZC = 2; 
} 
void loop() { 
if(ZC == 1){ 
// Enable external interrupt (INT0) 
        
 
    delayMicroseconds(alpha); 
    digitalWrite(scr1_gate, HIGH); 
    delay(2); 
    digitalWrite(scr1_gate, LOW); 
    alpha = analogRead(pot) * 7; 
    ZC = 0; 
  } 
  if(ZC == 2){ 
    delayMicroseconds(alpha); 
    digitalWrite(scr2_gate, HIGH); 
    delay(2); 
    digitalWrite(scr2_gate, LOW); 
    alpha = analogRead(pot) * 7; 
    ZC = 0; 
  } 
} 

#  Controlled single phase to single phase(mid point)step down cycloconverter with Arduino 
#define scr1_gate   8 
#define scr2_gate   9 
#define scr3_gate   10 
#define scr4_gate   11 
#define pot        
byte ZC = 0; 
A0 
uint16_t alpha; 
        
 
void setup(void) { 
  pinMode(scr1_gate, OUTPUT); 
  digitalWrite(scr1_gate, LOW); 
  pinMode(scr2_gate, OUTPUT); 
  digitalWrite(scr2_gate, LOW); 
  attachInterrupt(0, ZC_detect, CHANGE);   
   pinMode(scr3_gate, OUTPUT); 
  digitalWrite(scr3_gate, LOW); 
  pinMode(scr4_gate, OUTPUT); 
  digitalWrite(scr4_gate, LOW); 
  attachInterrupt(0, ZC_detect, CHANGE);  // Enable external interrupt (INT0) 
} 
void ZC_detect() { 
  if(digitalRead(2)) 
    ZC = 1; 
  else 
    ZC = 2; 
} 
void loop() { 
  if(ZC == 1){ 
    delayMicroseconds(alpha); 
    digitalWrite(scr1_gate, HIGH); 
    delay(2); 
    digitalWrite(scr1_gate, LOW); 
    alpha = analogRead(pot) * 7; 
    ZC = 0; 
    delayMicroseconds(alpha); 
    digitalWrite(scr3_gate, HIGH); 
    delay(2); 
    digitalWrite(scr3_gate, LOW); 
        
 
    alpha = analogRead(pot) * 7; 
    ZC = 0; 
  } 
  if(ZC == 2){ 
    delayMicroseconds(alpha); 
    digitalWrite(scr2_gate, HIGH); 
    delay(2); 
    digitalWrite(scr2_gate, LOW); 
    alpha = analogRead(pot) * 7; 
    ZC = 0; 
    delayMicroseconds(alpha); 
    digitalWrite(scr4_gate, HIGH); 
    delay(2); 
    digitalWrite(scr4_gate, LOW); 
    alpha = analogRead(pot) * 7; 
    ZC = 0;    
  } 
} 

# Controlled single phase AC-AC voltage contoller with Arduino 
#define scr1_gate   8 
#define scr2_gate   9 
#define pot        
byte ZC = 0; 
uint16_t alpha; 
A0 
void setup(void) { 
pinMode(scr1_gate, OUTPUT); 
digitalWrite(scr1_gate, LOW); 
pinMode(scr2_gate, OUTPUT); 
digitalWrite(scr2_gate, LOW); 
attachInterrupt(0, ZC_detect, CHANGE);       
} 
// Enable external interrupt (INT0) 
        
 
void ZC_detect() { 
  if(digitalRead(2)) 
    ZC = 1; 
  else 
    ZC = 2; 
} 
void loop() { 
  if(ZC == 1){ 
    delayMicroseconds(alpha); 
    digitalWrite(scr1_gate, HIGH); 
    delay(2); 
    digitalWrite(scr1_gate, LOW); 
    alpha = analogRead(pot) * 7; 
    ZC = 0; 
  } 
  if(ZC == 2){ 
    delayMicroseconds(alpha); 
    digitalWrite(scr2_gate, HIGH); 
    delay(2); 
    digitalWrite(scr2_gate, LOW); 
    alpha = analogRead(pot) * 7; 
    ZC = 0; 
  } 
}
