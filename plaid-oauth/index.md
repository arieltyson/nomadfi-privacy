---
layout: default
title: NomadFi — returning to the app
---

<noscript>
<p>
This page exists so NomadFi's iOS app can return you after a bank
finishes authorizing a read-only financial connection.
</p>
<p>
If you are reading this in a web browser, JavaScript appears to be
disabled. You can return to NomadFi manually by tapping the app icon
on your home screen.
</p>
</noscript>

<p id="status">Returning you to NomadFi…</p>

<script>
// When iOS sees this page via Plaid's OAuth redirect, the app's
// associated-domains entitlement intercepts the request and hands
// control to NomadFi. This fallback copy is only shown if the user
// lands here without the app installed.
(function () {
  var statusEl = document.getElementById('status');
  setTimeout(function () {
    if (statusEl) {
      statusEl.textContent =
        'If NomadFi did not reopen automatically, tap the app icon on your home screen.';
    }
  }, 2500);
})();
</script>
