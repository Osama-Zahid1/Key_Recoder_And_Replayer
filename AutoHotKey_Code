; Define the keys to record
keys := ["w", "a", "s", "d", "l", "Shift"]

; Variables to store recorded data
recordedKeys := []
recordedTimes := []
isRecording := false

; Hotkey to start/stop recording (F8 key)
F8::
    if isRecording {
        isRecording := false
        MsgBox, Recording Stopped.
    } else {
        recordedKeys := []
        recordedTimes := []
        StartTime := A_TickCount
        isRecording := true
        MsgBox, Recording Started.
    }
return

; Record key presses (handle each key separately)
~*w::
    RecordKey("w")
return

~*a::
    RecordKey("a")
return

~*s::
    RecordKey("s")
return

~*d::
    RecordKey("d")
return

~*l::
    RecordKey("l")
return

~*Shift::
    RecordKey("Shift")
return

; Function to record key presses
RecordKey(key) {
    global isRecording, recordedKeys, recordedTimes, StartTime
    if isRecording {
        recordedKeys.Push(key)
        recordedTimes.Push(A_TickCount - StartTime)
    }
}

; Hotkey to replay the recorded sequence (F9 key)
F9::
    if recordedKeys.MaxIndex() {
        MsgBox, Replaying recorded keys...
        StartTime := A_TickCount
        Loop, % recordedKeys.MaxIndex() {
            key := recordedKeys[A_Index]
            SleepDuration := recordedTimes[A_Index] - (A_TickCount - StartTime)
            if (SleepDuration > 0) {
                Sleep, %SleepDuration%
            }
            ; Simulate the key press
            Send, {%key% down}
            Sleep, 50 ; Hold the key down briefly
            Send, {%key% up}
        }
        MsgBox, Finished replaying recording.
    } else {
        MsgBox, No recording to replay.
    }
return

; Exit script (F10 key)
F10::ExitApp
