    1.
        
        db.people.find({ "scores" : { $all : [ { "$elemMatch" : { score: { $gte: 87, $lte: 96 } } } ] } });
    2.
        
        db.people.aggregate({ $unwind: "$scores" }, { $match: { "scores.type" : "exam", "scores.score": { $gt: 90 } } });

    3.
        
        db.people.update({ "name" : "Dusti Lemmond" }, { $set : { "accepted": true }}, { multi: true } );
