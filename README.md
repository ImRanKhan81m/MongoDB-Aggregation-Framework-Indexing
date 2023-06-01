# MongoDB-Aggregation-Framework-Indexing


# facet operator

```db.practice.aggregate([
    {
        $match: { _id: ObjectId("6406ad63fc13ae5a40000066") }
    },
    {
        $facet: {
            "friendsCount": [
                {
                    $project: { friendsCount: { $size: "$friends" } }
                }
            ],
            "interestsCount": [
                {
                    $project: { interestCount: { $size: "$interests" } }
                }
            ],
            "skillsCount": [
                {
                    $project: { skillsCount: { $size: "$skills" } }
                }
            ]
        }
    }
])
```

# Lookup operator

``` db.practice.aggregate([
    {
        $match: { _id: ObjectId("6406ad63fc13ae5a40000066") }
    },
    {
        $lookup: {
               from: "additionalInfo",
               localField: "_id",
               foreignField: "userId",
               as: "additionalInformation"
             }
    }

]) 
```
