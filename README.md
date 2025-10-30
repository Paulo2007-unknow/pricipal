using System;

public class Program
{
    public static void Main(string[] args)
    {
        Console.WriteLine("Ingresa el número de elementos que tendrá el array:");
        
        if (!int.TryParse(Console.ReadLine(), out int tamañoArray))
        {
            return;
        }

        int[] arrayOrigen = new int[tamañoArray];

        Console.WriteLine($"Ingresa los {tamañoArray} elementos uno por uno:");
        for (int i = 0; i < tamañoArray; i++)
        {
            Console.Write($"Elemento [{i}]: ");
            if (!int.TryParse(Console.ReadLine(), out arrayOrigen[i]))
            {
                return;
            }
        }
        
        // Declarar e inicializar el segundo array (Destino)
        int[] arrayDestino = new int[tamañoArray];

        // Copiar los elementos del array Origen al array Destino (usando el bucle for)
        for (int i = 0; i < arrayOrigen.Length; i++)
        {
            arrayDestino[i] = arrayOrigen[i];
        }

        // Mostrar el contenido del array Destino
        Console.WriteLine("\nContenido del Array Destino (Copiado):");
        Console.Write("[ ");
        
        for (int i = 0; i < arrayDestino.Length; i++)
        {
            Console.Write(arrayDestino[i]);
            if (i < arrayDestino.Length - 1)
            {
                Console.Write(", ");
            }
        }
        Console.WriteLine(" ]");
    }
}
