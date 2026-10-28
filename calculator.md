---
layout: single
title: Savings Calculator
description: "Compare Tempo and TrueTime costs by Jira site size."
toc: false
---

Tempo bills per Jira seat. TrueTime bills per Jira site user.
Marketplace bills both apps by site size, not by time tracker.
Enter your site size. See the difference.

<label>Jira site users: <input id="seats" type="number" value="200" min="1"></label>
<button onclick="calc()">Compare</button>
<p id="result"></p>

<script>
function calc() {
  var seats = Math.max(1, parseInt(document.getElementById('seats').value) || 0);
  var tempo = seats * 5.21;
  var truetime = seats <= 10 ? 0 : seats * 2.99;
  var save = tempo - truetime;
  document.getElementById('result').textContent =
    'Tempo: $' + tempo.toFixed(0) + ' per month. TrueTime: $' + truetime.toFixed(0) +
    ' per month. You save $' + save.toFixed(0) + ' per month ($' + (save * 12).toFixed(0) + ' per year).';
}
calc();
</script>

Example: 200 Jira site users. Tempo costs $1,042 per month. TrueTime costs $598 per month. You save $444 per month, $5,328 per year.

Price is USD 2.99 per user per month for all tiers above 10 users.
Tempo price comes from its public Marketplace listing, checked October 2026.
