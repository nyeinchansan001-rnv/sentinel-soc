---

# Day 5 – Web Attack Detection

## View Apache Logs

```spl
index=* sourcetype=access_combined
```

---

## Find 404 Errors

```spl
index=* sourcetype=access_combined status=404
```

---

## Find Login Requests

```spl
index=* sourcetype=access_combined "/login.php"
```

---

## Find Admin Page Requests

```spl
index=* sourcetype=access_combined "/admin"
```

---

## Show Important Fields

```spl
index=* sourcetype=access_combined
| table _time clientip method uri_path status useragent
```

---

## Purpose

These searches help identify suspicious web activity, failed requests, login attempts, and access to sensitive resources.
