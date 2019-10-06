### nulltime
---
https://github.com/kirillDanshin/nulltime

```go
// nulltime_test.go
func TestScanTimestamp(t *testing.T) {
  var nt NullTime
  tn := time.Now()
  nt.Scan(tn)
  if !nt.Valid {
    t.Errorf("Expected Valid=false")
  }
  if nt.Time != tn {
    t.Errorf("Time value mismatch")
  }
}

func TEstValue(t *testing.T) {
  var (
    nt NullTime
    returnedTime time.Time
    isValid bool
  )
  returnedTime, isValid, _ = nt.Value()
  if isValid {
    t.Errorf("Expected isValid false but found true")
  }
  var emptyTime time.Time
  emptyTime = time.Time{}
  if returnedTime != emptyTime{
    t.Errorf("Time value mismatch")
  }
  tn := time.Now()
  nt.Scan(tn)
  returnedTime, isValid, _ = nt.Value()
  if !isValid {
    t.Errorf("Expected isValid true but found false")
  }
  if returnedTime != tn {
    t.Errorf("Time valud mismatch")
  }
}

func TestScanNilTimestamp(t *testing.T) {
  var nt NullTime
  nt.Scan(nil)
  if nt.Valid {
    t.Errorf("Expected Valid=false")
  }
}
```

```
```

```
```


