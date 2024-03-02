mongosh


use student_database

db.createCollection("academic_records")
db.createCollection("co_curricular_activities")


db.academic_records.insertOne({
    student_id: 1,
    name: "Shivam Behera",
    grades: {
      math: 92,
      science: 88,
      english: 95
    },
    subjects: [
        "math",
        "science",
        "english"
    ]
})
  

db.co_curricular_activities.insertOne({
    student_id: 1,
    name: "Shivam Behera",
    activity_type: "Sports",
    duration: "1 year",
    achievements: [
        "First place in chess tournament",
        "Participation in science club"
    ]
})


// CREATE
db.academic_records.insertMany([
    {
    student_id: 2,
    name: "Omkar",
    grades: {
      math: 91,
      science: 89,
      english: 94
        },
    subjects: [
            "math",
            "science",
            "english"
        ]
    },
    {
    student_id: 3,
    name: "Aditya",
    grades: {
      math: 91,
      science: 78,
      english: 80
        },
    subjects: [
            "math",
            "science",
            "english"
        ]
    },
    {
        student_id: 4,
        name: "Rohit",
        grades: {
          math: 70,
          science: 98,
          english: 90
        },
        subjects: [
            "math",
            "science",
            "english"
        ]
    },
    {
            student_id: 5,
            name: "Xtreme",
            grades: {
              math: 70,
              science: 91,
              english: 88
        },
            subjects: [
            "math",
            "science",
            "english"
        ]
    },
])
  
  db.co_curricular_activities.insert([
    {
    student_id: 2,
    name: "Omkar",
    activity_type: "Music",
    duration: "2 years",
    achievements: [
            "Played violin in school orchestra"
        ]
    },
    {
        student_id: 3,
        name: "Aditya",
        activity_type: "Cricket",
        duration: "4 years",
        achievements: [
            "Played cricket in school ground"
        ]
    },
    {
            student_id: 4,
            name: "Rohit",
            activity_type: "Football",
            duration: "1 years",
            achievements: [
            "Played footbnall in state level"
        ]
    },
    {
                student_id: 5,
                name: "Xtreme",
                activity_type: "Arts",
                duration: "5 years",
                achievements: [
            "Got firts prize in arts"
        ]
    },
])
  
// Read

db.academic_records.find({ student_id: 1
})


db.co_curricular_activities.find({ student_id: 1
})


// UPDATE

db.academic_records.update({ student_id: 1
},
{ $set: { grades: { math: 95, science: 90, english: 94
        }
    }
})


db.co_curricular_activities.update({ student_id: 1
},
{ $push: { achievements: "Second place in debate competition"
    }
})

  
// Delete

db.academic_records.remove({ student_id: 2 })


db.co_curricular_activities.remove({ student_id: 2 })
