# algorytmy

1. Algorytm nierekurencyjny generujący najmniejsza liczbe permutacji przez transpozycje. / JS

function B(m, i) {
  if ((m % 2 === 0) && (m > 2)) {
    if (i < (m - 1)) {
      return i;
    } else {
      return m - 2;
    }
  } else {
    return m - 1;
  }
}

function power(n) {
  var countPower = n;
  while (n > 1) {
    countPower = countPower * (n - 1);
    n = n - 1;
  }
  return countPower;
}

function perm(n) {
  var count = power(n);
  var x;
  var i;
  var output;
  var placeholder;

  for (var a = 1; a < count + 1; a++) {

    output = "";
    for (var c = 1; c < p.length; c++) {
      output = output + " "+ p[c];
    }
    console.log(output);

    for (var b = 1; b < n; b++) {
      if (a % power(b) === 0) {
        x = b + 1;
        i = ((a / power(b)) % x);

        if (i !== 0) {
          placeholder = p[B(x, i)];
          p[B(x, i)] = p[x];
          p[x] = placeholder;
        }
      }
    }
  }
}


function main(input) {
  p = [];

  for (var i = 0; i <= input; i++) {
    p[i] = i;
  }
  perm(input);
}

main(3); // tutaj liczba elementow
