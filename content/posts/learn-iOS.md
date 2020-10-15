+++
title = "Learn iOS development"
date = "2020-05-12"
author = "Benjamin Cai"
description = "The Road I learn iOS develop"
showFullContent = false
+++


## iOS develop


### Protocal and delegates
 
Protocal can assign some function to classes while classes dont need to know the func specifically
only when the class is assigned delegate


```Swift
protocal AdvancedLifeSupport{
    func performCPR()
}

// any class has the delegate AdvancedLifeSupport has the method performCPR()


struct Paramedic: AdvancedLifeSupport {
    init(handler:EmergencyCallHandler){
        handler.delegate = self
    }

    func performCPR() {
        print("The paramedic does chest compressions, 30 per second.")
    }
}
// struct can have func method from delegate
// class can as well
```