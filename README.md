# 2021.04.26

WEEK09

01
--------
```c
#include <windows.h>
#include <stdio.h>   ///為了getchar
int main()
{
    char c;
    while(1)
    {
        c=getchar();
        PlaySound("do.wav",NULL,SND_ASYNC);
    }

}
```

02
----
```c
#include <windows.h>
#include <GL/glut.h>
void display()
{
    glClear(GL_COLOR_BUFFER_BIT|GL_DEPTH_BUFFER_BIT);
    glutSolidTeapot(0.3);
    glutSwapBuffers();
}
void keyboard(unsigned char key,int x,int y)
{
    if(key=='1')PlaySound("do.wav",NULL,SND_ASYNC);
    if(key=='2')PlaySound("re.wav",NULL,SND_ASYNC);
    if(key=='3')PlaySound("mi.wav",NULL,SND_ASYNC);
    if(key=='4')PlaySound("fa.wav",NULL,SND_ASYNC);
    if(key=='5')PlaySound("so.wav",NULL,SND_ASYNC);
}
int main(int argc,char**argv)
{
    glutInit(&argc,argv);
    glutInitDisplayMode(GLUT_DOUBLE|GL_DEPTH);
    glutCreateWindow("08160554");
    glutDisplayFunc(display);
    glutKeyboardFunc(keyboard);
    glutMainLoop();
}

```

03
----
```c
#include <windows.h>
#include <GL/glut.h>
void display()
{
    glClear(GL_COLOR_BUFFER_BIT|GL_DEPTH_BUFFER_BIT);
    glutSolidTeapot(0.3);
    glutSwapBuffers();
}
void keyboard(unsigned char key,int x,int y)
{
    if(key=='1')PlaySound("do.wav",NULL,SND_ASYNC);
    if(key=='2')PlaySound("re.wav",NULL,SND_ASYNC);
    if(key=='3')PlaySound("mi.wav",NULL,SND_ASYNC);
    if(key=='4')PlaySound("fa.wav",NULL,SND_ASYNC);
    if(key=='5')PlaySound("so.wav",NULL,SND_ASYNC);
}
void mouse(int button, int state, int x, int y)
{
   if(state==GLUT_DOWN) PlaySound("shot.wav",NULL,SND_ASYNC);
}
int main(int argc,char**argv)
{
    glutInit(&argc,argv);
    glutInitDisplayMode(GLUT_DOUBLE|GL_DEPTH);
    glutCreateWindow("08160554");
    glutDisplayFunc(display);
    glutKeyboardFunc(keyboard);
    glutMouseFunc(mouse);
    glutMainLoop();
}
```

04
----
```c
#include <windows.h>
#include <GL/glut.h>
#include "CMP3_MCI.h"
CMP3_MCI mp3;
void display()
{
    glClear(GL_COLOR_BUFFER_BIT|GL_DEPTH_BUFFER_BIT);
    glutSolidTeapot(0.3);
    glutSwapBuffers();
}
void keyboard(unsigned char key,int x,int y)
{
    if(key=='1')PlaySound("do.wav",NULL,SND_ASYNC);
    if(key=='2')PlaySound("re.wav",NULL,SND_ASYNC);
    if(key=='3')PlaySound("mi.wav",NULL,SND_ASYNC);
    if(key=='4')PlaySound("fa.wav",NULL,SND_ASYNC);
    if(key=='5')PlaySound("so.wav",NULL,SND_ASYNC);
}
void mouse(int button, int state, int x, int y)
{
   if(state==GLUT_DOWN) PlaySound("shot.wav",NULL,SND_ASYNC);
}
int main(int argc,char**argv)
{
    mp3.Load("music.mp3");
    mp3.Play();
    glutInit(&argc,argv);
    glutInitDisplayMode(GLUT_DOUBLE|GL_DEPTH);
    glutCreateWindow("08160554");
    glutDisplayFunc(display);
    glutKeyboardFunc(keyboard);
    glutMouseFunc(mouse);
    glutMainLoop();
}

```

05
----
```c
#include <GL/glut.h>
void display()
{
    glClear(GL_COLOR_BUFFER_BIT|GL_DEPTH_BUFFER_BIT);
    glutSolidTeapot(0.3);
    glutSwapBuffers();
}
const GLfloat light_ambient[]  = { 0.0f, 0.0f, 0.0f, 1.0f };
const GLfloat light_diffuse[]  = { 1.0f, 1.0f, 1.0f, 1.0f };
const GLfloat light_specular[] = { 1.0f, 1.0f, 1.0f, 1.0f };
const GLfloat light_position[] = { 2.0f, 5.0f, 5.0f, 0.0f };

const GLfloat mat_ambient[]    = { 0.7f, 0.7f, 0.7f, 1.0f };
const GLfloat mat_diffuse[]    = { 0.8f, 0.8f, 0.8f, 1.0f };
const GLfloat mat_specular[]   = { 1.0f, 1.0f, 1.0f, 1.0f };
const GLfloat high_shininess[] = { 100.0f };

int main(int argc,char**argv)
{

    glutInit(&argc,argv);
    glutInitDisplayMode(GLUT_DOUBLE|GL_DEPTH);
    glutCreateWindow("08160554");
    glEnable(GL_DEPTH_TEST);
    glDepthFunc(GL_LESS);

    glEnable(GL_LIGHT0);
    glEnable(GL_NORMALIZE);
    glEnable(GL_COLOR_MATERIAL);
    glEnable(GL_LIGHTING);

    glLightfv(GL_LIGHT0, GL_AMBIENT,  light_ambient);
    glLightfv(GL_LIGHT0, GL_DIFFUSE,  light_diffuse);
    glLightfv(GL_LIGHT0, GL_SPECULAR, light_specular);
    glLightfv(GL_LIGHT0, GL_POSITION, light_position);

    glMaterialfv(GL_FRONT, GL_AMBIENT,   mat_ambient);
    glMaterialfv(GL_FRONT, GL_DIFFUSE,   mat_diffuse);
    glMaterialfv(GL_FRONT, GL_SPECULAR,  mat_specular);
    glMaterialfv(GL_FRONT, GL_SHININESS, high_shininess);
    glutDisplayFunc(display);
    glutMainLoop();
}
```

06
----
```c
#include <GL/glut.h>
void display()
{
    glClear(GL_COLOR_BUFFER_BIT|GL_DEPTH_BUFFER_BIT);
    glutSolidTeapot(0.3);
    glutSwapBuffers();
}
const GLfloat light_ambient[]  = { 0.0f, 0.0f, 0.0f, 1.0f };
const GLfloat light_diffuse[]  = { 1.0f, 1.0f, 1.0f, 1.0f };
const GLfloat light_specular[] = { 1.0f, 1.0f, 1.0f, 1.0f };
const GLfloat light_position[] = { 2.0f, -5.0f, -5.0f, 0.0f };

const GLfloat mat_ambient[]    = { 0.7f, 0.7f, 0.7f, 1.0f };
const GLfloat mat_diffuse[]    = { 0.8f, 0.8f, 0.8f, 1.0f };
const GLfloat mat_specular[]   = { 1.0f, 1.0f, 1.0f, 1.0f };
const GLfloat high_shininess[] = { 100.0f };

int main(int argc,char**argv)
{

    glutInit(&argc,argv);
    glutInitDisplayMode(GLUT_DOUBLE|GL_DEPTH);
    glutCreateWindow("08160554");
    glEnable(GL_DEPTH_TEST);
    glDepthFunc(GL_LESS);

    glEnable(GL_LIGHT0);
    glEnable(GL_NORMALIZE);
    glEnable(GL_COLOR_MATERIAL);
    glEnable(GL_LIGHTING);

    glLightfv(GL_LIGHT0, GL_AMBIENT,  light_ambient);
    glLightfv(GL_LIGHT0, GL_DIFFUSE,  light_diffuse);
    glLightfv(GL_LIGHT0, GL_SPECULAR, light_specular);
    glLightfv(GL_LIGHT0, GL_POSITION, light_position);

    glMaterialfv(GL_FRONT, GL_AMBIENT,   mat_ambient);
    glMaterialfv(GL_FRONT, GL_DIFFUSE,   mat_diffuse);
    glMaterialfv(GL_FRONT, GL_SPECULAR,  mat_specular);
    glMaterialfv(GL_FRONT, GL_SHININESS, high_shininess);
    glutDisplayFunc(display);
    glutMainLoop();
}


```
