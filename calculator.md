---
layout: single
title: Savings Calculator
toc: false
---

Tempo bills per Jira seat. TrueTime bills per person who tracks time.
Enter your numbers. See the difference.

<label>Jira seats: <input id="seats" type="number" value="200" min="1"></label>
<label>People who track time: <input id="trackers" type="number" value="15" min="0"></label>
<button onclick="calc()">Compare</button>
<p id="result"></p>

<script>
function calc() {
  var seats = Math.max(1, parseInt(document.getElementById('seats').value) || 0);
  var trackers = Math.max(0, parseInt(document.getElementById('trackers').value) || 0);
  var tempo = seats * 5.21;
  var truetime = trackers <= 10 ? 0 : trackers * 2.99;
  var save = tempo - truetime;
  document.getElementById('result').textContent =
    'Tempo: $' + tempo.toFixed(0) + ' per month. TrueTime: $' + truetime.toFixed(0) +
    ' per month. You save $' + save.toFixed(0) + ' per month ($' + (save * 12).toFixed(0) + ' per year).';
}
calc();
</script>

Example: 200 seats, 15 trackers. Tempo costs $1,042 per month. TrueTime costs $45 per month. You save $997 per month, $11,966 per year.

Note: price above 100 trackers is not set yet. This calculator uses $2.99 for all paid trackers.
Tempo price comes from its public Marketplace listing, checked October 2026.
