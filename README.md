# Perl_Programming_Notes
learning Perl programming language

<h3>Perl Basic</h3>

Ternary :

```Perl
$hasil = ($b%$a == 0) ? ($c%$a == 0) ? ifTrue1 : ifTrue2 : ifFalse;
```

Input console :

```Perl
$input = <STDIN>;
```

Substring ;

```Perl
$parameter = substr $inputString, 11, 5; # dimulai dari karakter ke 11, dengan panjang 5 karakter kedepan
```

Array :

```Perl
$value = 10;
@arr1 = (0,0,0);
@arr2 = (0,0,0);
@array = (\@arr1,\@arr2);
$array[1,1] = $value; #can be insert char etc.
```

<h3>Perl Basic (Web)</h3>

Basic Perl web :

```Perl
# perl execution path
#! C:/xampp/perl/bin/perl.exe
# atau C:/strawberry/perl/bin/perl.exe

print "Content-type: text/html\n\n";  # send html command
print "<p>aaaaa test aaaaa</p>";      # html content
```

Contact with the database :

```Perl
# init koneksi ke database lokal / remote db
$conn = DBI->connect("dbi:jenisDB:db=PATH;", "username", "password"); #target db

# query
$param1 = $conn->prepare("query_here");
$param1->execute();

# parameter digunakan untuk binding
$param2 = $conn->prepare("query here WHERE id = ?");
$param2->execute($value);

while (@result=$param2->fetchrow_array()){
  print($result[0]);
}

$conn->disconnect();
```

File operation :

```Perl
open(FAS,">temporaryFiles/printTest.txt");
  print FAS qq~       --------------------         \n~;
  print FAS qq~       |    Print Here    |         \n~;
  print FAS qq~       --------------------         \n~;
close(FAS);
```
