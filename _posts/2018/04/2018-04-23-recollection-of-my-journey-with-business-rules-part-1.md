---
layout: post
title: 'Recollection of my journey with Business Rules - Part 1'
categories: [Programming]
tags: []
date: 2018-04-23 02:30:00 PM UTC
---

<!-- April 23, 2018 10:30:00 PM Philippine Time -->
<!-- December 20, 2017 2:20:00 AM Philippine Time -->


There are lot's of reasons why one writes blog posts. One of them is this: _so that he will have something to laught at when he gets older._

This post might be one of those posts I will laugh at when I get older... It sound like I'm bragging about my old but insignificant work! :laughing: Who cares, right? It might be insignificant to others, but it was significant to me.

So here we go...

In my five years of experience working as a programmer I have come into a deeper appreciation of the importance of separating the business rules from the other parts of a software system.

<!--more-->

Since college I've been on search on how to best structure a software system.

I remember encountering this idea of 3-layers architecture in college --- _Presentation layer, Business Logic layer (BLL), and Data Access layer (DAL)_. But during that time, I do not yet fully understand the _"why"_ part of the separation.

Today, I already understand why: the separation makes the software _soft_, that is easy to maintain. Maintainability is important because, like what they say, maintenance comprises 80% of the life of a software system.

<!--more-->


I remember using this 3-layers thing in one, and only one, of my projects at school. What I remember doing in that project is placing the validation in the _BLL_, and placing all the SQL in the _DAL_.

_"I wonder what I really did in that project..."_

Sometimes I just want to know what happened in the past.

...So I tried to look for that project in my old files. 

_Tada!!! I found it:_ ["StudInfoSys_VB.NETProj - 4.8"](https://drive.google.com/open?id=0B99bQWWl3cfxYnBEdFA5RFVRU3kwVkV6bVBYUVgyUQ)

There!... This part contains the validation I was talking about in [a previous post.](/2018/03/21/on-maintainability-and-the-separation-of-business-rules)

``` vb
Public Class StudentBLL
    ...
    Public Sub InsertStudent(ByVal FirstName As String, ...)
        ...
        If FirstName.Trim() = "" Then
            Throw New Exception("First Name is required")
        End If
        If LastName.Trim() = "" Then
            Throw New Exception("Last Name is required")
        End If
        
        studDAL.OpenConnection(connectionString)
        studDAL.InsertStudent(FirstName, ...)
        studDAL.CloseConnection()
    End Sub
    ...
End Class
```

``` vb 
Public Class StudentDAL
    ...
    Public Sub InsertStudent(ByVal FirstName As String, ...)
        Dim sqlstr As String = String.Format("INSERT INTO Students " & ...

        Using cmd As New OleDbCommand(sqlstr, Me.oledbConn)
            cmd.ExecuteNonQuery()
        End Using
    End Sub
    ...
End Class
```

```
Modified: Thursday, ‎16 ‎February ‎2012, ‏‎11:43:22 PM
```

_It was written in VB.NET?... in 2012?_

_Why? I think during this time, I am already using C# as my primary programming language!..._

Maybe it was a requirement at school to use VB.NET? I'm not sure... But maybe I just wanted to challenge myself whether I can still write in VB.NET during that time? Perhaps... I'm not sure.

_But perhaps this project is not mine!?..._

I tried to look for some hints in the project so that I can be sure that this truly is mine...

``` vb
Public Class StudentBLL

...
...


'Created: February 17, 2012 7:00 PM to 2:00 AM the next day
```

_That sounds like me..._  :smile:

_And it truly is written in 2012!!_

But I'm sure that I knew about this 3-layers thing before 2012!...

_But_ I remember using it only in _one_ and only one project! And because this project is confirmed as mine, this must be _that_ project where I tried to use this 3-layers thing!

_Hmmmm... Something must be wrong..._

_Ahh!!!_

I found another project... written in C#... created in 2010! It has a _DAL_, but no _BLL_: ["StudInfoSys(TypedDataSets)"](https://drive.google.com/open?id=0B99bQWWl3cfxM2NkOTcyYTctZWJlZi00ODMyLTg3NWQtMmQxMTAxZjMyMmM0)


``` csharp
public partial class StudentForm : Form
{

// [in line 719]
    private void subjectIDComboBox_SelectedValueChanged(object sender, EventArgs e)
    {
        try
        {
            if (((ComboBox)sender).SelectedIndex == -1)
            {
                descriptiveTitleTextBox.Text = "";
                return;
            }

            string currSubjectID = subjectIDComboBox.Text;

            var subjects = from s in studInfoSysDataSet.Subjects
                            where s.SubjectID == currSubjectID
                            select s;

            //Descriptive title of currently selected SubjectID
            if (subjects != null)
            {
                descriptiveTitleTextBox.Text = subjects.Single().DescriptiveTitle;
            }
        }
        catch (InvalidOperationException)
        {
            this.regSubjectsBindingNavigatorPositionItem.Text = "NONE";
        }
    }
}
```

So it is confirmed that in 2012 I am already familiar with C#.

_But Look at that mess... 700 lines of code... I packed everything in one Form... and the presentation layer knows about DataSets!" :laughing:_

In a good architecture, the DataSets are not supposed to be exposed to the presentation layer. But of course, I was naive during that time.

And also during that time, I liked the drag-and-drop things that Visual Studio provides :laughing: :laughing: :laughing: ... It makes the life of a programmer easier _(or so I thought)_. You just drag a GridView, change some properties in it to connect it to the database, and wa-la... you now have a working application!

In that kind of environment, with the drag-and-drop thing, the presentation layer is [tightly coupled](http://blog.ploeh.dk/2012/02/02/LooseCouplingandtheBigPicture/) to the data-access layer. Perhaps there was another way of doing it, without the [tight coupling](http://blog.ploeh.dk/2012/02/02/LooseCouplingandtheBigPicture/), but I think this was the only way I know how to do it during that time.

Of course I later understood that these drag-and-drop things are _evil_... I mean, you would _not_ want to _ab**use**_ it if you want your app to be maintainable (or something like that).

**_The End_**

:bow:
