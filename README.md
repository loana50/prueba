Module MainModule
    Sub Main()
        ' Solicitar la cantidad de niños que nacen mensualmente
        Console.Write("Ingrese la cantidad de niños que nacen mensualmente: ")
        Dim nacenMensualmente As Integer = Integer.Parse(Console.ReadLine())

        ' Estadísticas del DANE
        Dim muereCada10 As Integer = 2  ' De cada 10 niños, mueren 2

        ' Calcular cuántos mueren mensualmente
        Dim muerenMensualmente As Integer = (nacenMensualmente \ 10) * muereCada10

        ' Calcular cuántos viven mensualmente
        Dim vivenMensualmente As Integer = nacenMensualmente - muerenMensualmente

        ' Calcular cuántos viven anualmente
        Dim vivenAnualmente As Integer = vivenMensualmente * 12

        ' Calcular cuántos mueren anualmente
        Dim muerenAnualmente As Integer = muerenMensualmente * 12

        ' Verificar si hay alerta por cantidad de fallecidos anualmente (>100)
        Dim alerta As String = "No hay alerta"
        If muerenAnualmente > 100 Then
            alerta = "¡Alerta! Más de 100 niños mueren anualmente."
        End If

        ' Mostrar resultados en pantalla
        Console.WriteLine(vbCrLf & "=== Resultados ===")
        Console.WriteLine("Niños que nacen mensualmente: " & nacenMensualmente)
        Console.WriteLine("Niños que mueren mensualmente: " & muerenMensualmente)
        Console.WriteLine("Niños que viven mensualmente: " & vivenMensualmente)
        Console.WriteLine("Niños que viven anualmente: " & vivenAnualmente)
        Console.WriteLine("Niños que mueren anualmente: " & muerenAnualmente)
        Console.WriteLine("Estado de alerta: " & alerta)

        Console.ReadLine()
    End Sub
End Module
