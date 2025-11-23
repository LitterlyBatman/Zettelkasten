---
topic: development
---

 2025 - 12 - 23 12:44

tags: [[School]] [[CSharp]]

progress: >

# CSharp Learning Env

Dit is de documentatie pagina voor mijn C# leer omgeving. In deze omgeving maak ik kleine terminal gerichte opdrachten om mijn C# skills te verfijnen. In deze omgeving experimenteer ik met alles dat ik tegen kom over C#, in dit document documenteer ik mijn uitleg!

## Kleuren Gradient
---
![[Pasted image 20250523125054.png]]
(HSV kleuren code systeem voor computer graphics.)

In het programma gebruik ik een function om de terminal er wat beter uit te laten zien

```C#
static (int r, int g, int b) HSVtoRGB(float h, float s, float v)
{
    float c = v * s;
    float x = c * (1 - Math.Abs((h / 60f) % 2 - 1));
    float m = v - c;

    float r1 = 0, g1 = 0, b1 = 0;

    if (h < 60) (r1, g1, b1) = (c, x, 0);
    else if (h < 120) (r1, g1, b1) = (x, c, 0);
    else if (h < 180) (r1, g1, b1) = (0, c, x);
    else if (h < 240) (r1, g1, b1) = (0, x, c);
    else if (h < 300) (r1, g1, b1) = (x, 0, c);
    else (r1, g1, b1) = (c, 0, x);

    int r = (int)((r1 + m) * 255);
    int g = (int)((g1 + m) * 255);
    int b = (int)((b1 + m) * 255);

    return (r, g, b);
}
```
this line ensures the styling of 24bit colours can be used in the UTF-8 teminal
```C#
Console.OutputEncoding = System.Text.Encoding.UTF8;
```
these lines ensure that 
```C#
var rgb = HSVtoRGB((i / (float)methods.Length) * 300f, 1f, 1f); // 0°–300° rainbow span
string ansi = $"\u001b[38;2;{rgb.r};{rgb.g};{rgb.b}m";
Console.WriteLine($"{ansi}{i + 1}: {methods[i].Name}\u001b[0m");
```
**Refrences**
--
