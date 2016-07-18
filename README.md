    1.
        
         db.people.find({ "scores.score": { $gt: 87, $lt: 93 } } );

    2.
        
        db.people.aggregate({ $unwind: "$scores" }, { $match: { "scores.type" : "exam", "scores.score": { $gt: 90 } } });

    3.
        
        db.people.update({ "name" : "Dusti Lemmond" }, { $set : { "accepted": true }}, { multi: true } );
