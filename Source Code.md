# Source Code

Imports System.Reflection.Emit
Imports System.Runtime.InteropServices.WindowsRuntime

Public Class Form1
    Private Const Text1 As String = "The infomation has been saved."

    'Function to calculate the length and the width of the liner. 
    '                                                                    Two decimals so it can return two decimals
    Private Function linerCalculations(length As Decimal, width As Decimal, depth As Decimal) As (Decimal, Decimal)
        'Calculates liner length
        Dim linerLength As Decimal = length + (2 * depth)
        'Calculates liner width
        Dim linerWidth As Decimal = width + (2 * depth)
        'Return to program so area can be calculated. 
        Return (linerLength, linerWidth)
    End Function

    'This function calculates the length and width of the liner which will be used
    Private Sub Timer1_Tick(sender As Object, e As EventArgs) Handles Timer1.Tick
        'Displays the current date
        lblDate.Text = Date.Now.ToString("dd-MM-yyyy")
        'Displays the current time
        lblTime.Text = Date.Now.ToString("hh:mm:ss")
    End Sub

    Private Sub btnQuit_Click(sender As Object, e As EventArgs) Handles btnQuit.Click
        'Closes the program when the quit button is clicked
        Me.Close()
    End Sub

    Private Sub btnCalculate_Click(sender As Object, e As EventArgs) Handles btnCalculate.Click
        'Ceclare varibales 
        Dim length, depth, width, area, cost, linerLength, linerWidth As Decimal
        Dim valid As Integer
        Dim liner
        Dim name, ref As String
        'Assigns textbox contents to variables
        length = txtLength.Text
        depth = txtDepth.Text
        width = txtWidth.Text
        name = txtName.Text
        ref = txtReference.Text

        'Converts from string to a decimal so it can carry out validation
        length = Convert.ToDecimal(txtLength.Text)
        width = Convert.ToDecimal(txtWidth.Text)
        depth = Convert.ToDecimal(txtDepth.Text)


        'Checks if the length is above the accepted range
        If length > 10 Then
            MessageBox.Show("Your length is above the maximum range of 10 metres.")
            txtLength.Clear()
            'valid = 1 represents false input
            valid = 1
        End If
        'Checks if length is below the minimum range
        If length < 0.5 Then
            MessageBox.Show("Your length is below the minimum range of 0.5 metres")
            txtLength.Clear()
            'valid = 1 represents false input
            valid = 1
        End If

        'Checks if width is above the accepted range
        If width > 10 Then
            MessageBox.Show("Your width is above the maximum range of 10 metres")
            txtWidth.Clear()
            'valid = 1 represents false input
            valid = 1

        End If

        'Checks is the widthg is below the minimum range 
        If width < 0.5 Then
            MessageBox.Show("Your width is below the minimum range of 0.5 metres")
            txtWidth.Clear()
            'valid = 1 represents false input
            valid = 1

        End If

        'Checks if depth is above the accepted range
        If depth > 2 Then
            MessageBox.Show("Your depth is above the accepted range of 2 metres")
            txtDepth.Clear()
            'valid = 1 represents false input
            valid = 1

        End If

        'Checks if the depth is below the minumum range of 0.5 metres
        If depth < 0.5 Then
            MessageBox.Show("The depth is below the accepoted range of 0.5 metres")
            txtDepth.Clear()
            'valid = 1 represents false input
            valid = 1
        End If

        If Len(name) < 1 Then
            MessageBox.Show("You must enter a name")
        End If

        If Len(ref) < 1 Then
            MessageBox.Show("You must enter a reference number")
        End If

        'Makes sure all the data entered is correct then assigns valid to 2 which represents true
        If length >= 0.5 And length <= 10 And width >= 0.5 And width <= 10 And depth >= 0.5 And depth <= 2 And Len(ref) > 1 And Len(name) > 1 Then
            valid = 2
        End If

        'Only runs if valid = 2 representing true
        If valid = 2 Then
            liner = linerCalculations(length, width, depth)
            linerLength = liner.Item1
            linerWidth = liner.Item2
            'Uses the calculated length and width to work out area
            area = linerLength * linerWidth
            'Calculates which liner gauge to use based on the area calculated.
            If area <= 15 Then
                cost = area * 1.12
                txtliner.Text = " GAUGE 1"
            ElseIf area > 15 Then
                cost = area * 1.76
                txtliner.Text = "GAUGE 2"
            End If
            'Outputs the calculation result stored in variable to textbox shown on the form. 
            txtArea.Text = area
            txtCost.Text = cost
        End If



    End Sub

    Private Sub btnVeiw_Click(sender As Object, e As EventArgs) Handles btnVeiw.Click
        'Opens text file called Order
        FileOpen(1, "Order.txt", OpenMode.Input)
        'While loop to print the content of the text document line by line into the lstOrder until there are no lines left to print. 
        While Not EOF(1)
            lstOrder.Items.Add(LineInput(1))
        End While
        'Closes the file once all the lines have been ouputted into lstOrder 
        FileClose(1)
    End Sub

    Private Sub btnSave_Click(sender As Object, e As EventArgs) Handles btnSave.Click
        Dim area, cost As Decimal
        Dim name, reference, gauge As String
        'Assigns textbox contents to variables
        'Assign the contents of thetextbox to a variable
        name = txtName.Text
        'Convertsdata type from string to an Decimal number 
        area = Convert.ToDecimal(txtArea.Text)
        cost = Convert.ToDecimal(txtCost.Text)
        gauge = txtliner.Text
        reference = txtReference.Text
        'Opens text file in append mode so data can be added to the end of the document.
        FileOpen(1, "Order.txt", OpenMode.Append)
        'Saves te content variables into the document but with added strings before to state their significance.
        PrintLine(1, "Name: " & name & "  Reference: " & reference & "  Area: " & area & "  Cost: £" & cost & "  Liner Gauge: " & gauge)
        'Closes the text file
        FileClose(1)
        'Tells the user their data has been saved in a message box which pops up
        MessageBox.Show("Your data has been saved successfully.")
        'Clears all data from the textboxes shown on the form. 
        txtArea.Clear()
        txtName.Clear()
        txtCost.Clear()
        txtReference.Clear()
        txtWidth.Clear()
        txtLength.Clear()
        txtDepth.Clear()
        txtliner.Clear()

    End Sub

    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles btnInstructions.Click
        MessageBox.Show("Instructions:" & vbCrLf & vbCrLf & "1. Input width, length, depth" & vbCrLf & "2. Click Calculate" & vbCrLf & "3. Clcik Save" & vbCrLf & "3. When you want to veiw the data click veiw")
    End Sub
End Class
