document.addEventListener("DOMContentLoaded", (event) => {
  const basePath =
    "https://raw.githubusercontent.com/SquishyPuma88/Plant_Images/main/";

  // Define lists for quiz data
  const genusList = [
    "Pachystegia",
    "Carmichaelia",
    "Rhopalostylis",
    "Astelia",
    "Ligularia",
    "Pratia",
    "Myosotidium",
    "Apodasmia",
    "Phormium",
    "Gaura",
    "Chionochloa",
    "Betula",
    "Acer",
    "Anemanthele",
    "Pittosporum",
    "Stachys",
    "Penstemon",
    "Lavendula",
    "Echinacea",
    "Sedum",
    "Arthropodium",
    "Dianella",
    "Pimelea",
    "Catalpa",
    "Melicytus",
    "Podocarpus",
    "Teucridium",
    "Coprosma",
    "Phormium",
    "Olearia",
    "Rubus",
    "Pittosporum",
    "Haloregis",
    "Libertia",
    "Poa",
    "Fuscospora",
    "Dacrydium",
    "Solanum",
    "Sceranthus",
    "Muehlenbeckia",
    "Euphorbia",
    "Fuscospora",
    "Agathis",
    "Pseudowintera",
    "Coprosma",
    "Sophora",
    "Cordyline",
    "Pseudopanax",
    "Pseudopanax"
  ];

  const speciesList = [
    "insignis",
    "stevensonii",
    "sapida",
    "chathamica",
    "dentata",
    "angulata",
    "hortensia",
    "similis",
    "cookianum",
    "lindheimeri",
    "flavicans",
    "pendula",
    "platanoides",
    "lessoniana",
    "tenuifolium",
    "byzantina",
    "scrophulariaceae",
    "angustifolia",
    "purpurea",
    "spectabile",
    "cirratum",
    "nigra",
    "prostrata",
    "bignonioides",
    "ramiflorus",
    "nivalis",
    "parvifolium",
    "rugosa",
    "tenax",
    "cheesemanii",
    "cissoides",
    "tenuifolium",
    "erecta",
    "peregrinans",
    "cita",
    "cliffortioides",
    "cupressinum",
    "laciniatum",
    "biflorus",
    "axillaris",
    "glauca",
    "fusca",
    "australis",
    "colorata",
    "propinqua",
    "microphylla",
    "australis",
    "crassifolius",
    "ferox"
  ];

  const commonNameList = [
    "Marlborough Rock Daisy",
    "Weeping Broom",
    "Nikau Palm",
    "Kakaha/Silver Spear",
    "Ligularia / Tractor Seat Plant",
    "Panakenake",
    "Chatham Island Forget-Me-Not",
    "Oioi Or Jointed Wire Rush",
    "Wharariki / Mountain Flax",
    "Gaura So White",
    "Miniature Toetoe",
    "Silver Birch",
    "Purple Norway Maple",
    "Hunangāmoho/Wind Grass",
    "Dwarf Pittosporum",
    "Lambs Ear",
    "Penstemon",
    "English Lavender",
    "Echinacea Or Cone Flower",
    "Sedum",
    "Rengarenga / Rock Lily",
    "Turutu",
    "NZ Daphne",
    "Indian Bean Tree",
    "Mahoe Or Whiteywood",
    "Snow (Or Mountain) Totara",
    "Teucridium",
    "Red Coprosma",
    "Harakeke / NZ Flax",
    "Streamside Daisy Or Cheesemanii's Daisy",
    "Tātarāmoa / Bush Lawyer",
    "Kohuhu Or Black Matipo",
    "Toatoa Or Fireweed",
    "NZ Iris",
    "Silver Tussock",
    "Mountain Beech",
    "Rimu",
    "Poroporo",
    "Sceranthus",
    "Creeping Muehlenbeckia",
    "Shore Spurge (Or Waiu-Atua)",
    "Red Beech",
    "Kauri",
    "Horopito (Or Pepper Tree)",
    "Mingimingi",
    "Weeping Kowhai Or Small Leaved Kowhai",
    "Tī Kōuka / Cabbage Tree",
    "Lancewood",
    "Fierce Lancewood"
  ];

  const growingConditionsList = [
    "Coastal conditions, full sun, well drained soil",
    "Alpine or alluvial conditions, full sun, moist, well drained soil",
    "Shaded gullies, moist soils, shelter from frost and wind",
    "Coastal conditions, part-shade, shelter from heavy frosts",
    "Forest conditions, part-full shade, moist, well-drained soil",
    "Part-shade, moist soil. Tolerates light disturbance",
    "Coastal and rocky conditions, full-part shade, moist, well-drained soil",
    "Wetland conditions, fresh water",
    "Coastal and alpine conditions. Tolerant of dry, cold and exposed conditions",
    "Full-sun, well-drained soil. Drought tolerant",
    "Coastal and sub-alpine conditions, moist well-drained soils, cold and wind tolerant",
    "Full sun to part shade, moist, well-drained soils",
    "Full-sun or part shade, tolerant of a range of conditions",
    "Forest-edge conditions, full sun to part-shade, tolerates disturbance",
    "Full-sun to part-shade. Drought and cold tolerant",
    "Well drained soil. Drought and humidity tolerant",
    "Full-sun, well-drained alkaline soils, drought tolerant",
    "Full-sun to part-shade. Heat and drought tolerant",
    "Coastal conditions, full-sun to full-shade, dry-to-moist soils",
    "Forest conditions, sun/semi shade, well drained, fertile, moist soil",
    "Coastal to alpine conditions",
    "Full-sun, moist, well-drained soil. Needs shelter",
    "Forest edge conditions, well drained soil, tolerates disturbance, sun/semi shade",
    "Alpine conditions, full sun, moist, fertile, well drained soil",
    "Alluvial conditions, full-sun to part-shade. Tolerates poor, dry soils",
    "Lowland to montane conditions, full-sun, dry to moist, well drained soils",
    "Alluvial, wetland and coastal conditions, full sun, tolerant of swampy to dry soils",
    "Alluvial and forest margin conditions, full-sun to part-shade, moist, well-drained soils",
    "Coastal to montane conditions. Found on margins of wetlands",
    "Full-sun to part-shade, well drained soils",
    "Coastal to montane conditions. Colonises disturbed sites such as forest margins and floodplains",
    "Full sun, well drained soil/ dry",
    "Coastal to montane conditions. Preference for disturbed sites",
    "Floodplains and grassland conditions, full-sun, moist, well-drained soil",
    "Forest conditions, full-sun to part-shade, moist, well drained, moist soil",
    "Forest conditions, full-sun to part-shade, poorly drained, swampy soils",
    "Forest conditions, sun/semi shade, well drained, fertile, moist soil",
    "Grows in a variety of conditions from well drained - wet soils, prefers full sun/part shade",
    "Most soil types if well drained, full sun/part shade",
    "Wetland to scrubland conditions, full-sun, drought-tolerant, does not tolerate shade"
  ];
  // Helper function to shuffle options and include the correct answer.
  function getShuffledOptions(correctAnswer, list) {
    const filteredList = list.filter((item) => item !== correctAnswer);
    return [
      correctAnswer,
      ...filteredList.sort(() => 0.5 - Math.random()).slice(0, 3)
    ];
  }

  const quizData = [
    {
      image: `${basePath}Bush_Lawyer.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Rubus", genusList),
        species: getShuffledOptions("cissoides", speciesList),
        commonName: getShuffledOptions(
          "Bush Lawyer / Tātarāmoa",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Coastal to montane conditions. Found on margins of wetlands.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Rubus",
        species: "cissoides",
        commonName: "Bush Lawyer / Tātarāmoa",
        growingConditions:
          "Coastal to montane conditions. Found on margins of wetlands."
      }
    },
    {
      image: `${basePath}Chatam_Island_Forget_Me_Not.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Myosotidium", genusList),
        species: getShuffledOptions("hortensia", speciesList),
        commonName: getShuffledOptions(
          "Chatham Island forget me not",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Coastal and rocky conditions, full-part shade, moist, well-drained soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Myosotidium",
        species: "hortensia",
        commonName: "Chatham Island forget me not",
        growingConditions:
          "Coastal and rocky conditions, full-part shade, moist, well-drained soil."
      }
    },
    {
      image: `${basePath}Cheesemanii_Daisy.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Olearia", genusList),
        species: getShuffledOptions("cheesemanii", speciesList),
        commonName: getShuffledOptions(
          "Cheesemanii's diasy / streamside daisy",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Alluvial and forest marigin conditions, full-sun to part-shade, moist, well-drained soils.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Olearia",
        species: "cheesemanii",
        commonName: "Cheesemanii's diasy / streamside daisy",
        growingConditions:
          "Alluvial and forest marigin conditions, full-sun to part-shade, moist, well-drained soils."
      }
    },
    {
      image: `${basePath}Creeping_Muehlenbeckia.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Muehlenbeckia", genusList),
        species: getShuffledOptions("axillaris", speciesList),
        commonName: getShuffledOptions(
          "creeping muehlenbeckia",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Floodplains and grassland conditions, full-sun, moist, well-drained soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Muehlenbeckia",
        species: "axillaris",
        commonName: "creeping muehlenbeckia",
        growingConditions:
          "Floodplains and grassland conditions, full-sun, moist, well-drained soil."
      }
    },
    {
      image: `${basePath}Dwarf_Pittosporum.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Pittosporum", genusList),
        species: getShuffledOptions("tenuifolium", speciesList),
        commonName: getShuffledOptions("dwarf pittosporum", commonNameList),
        growingConditions: getShuffledOptions(
          "Forest-edge conditions, full sun to part-shade, tolerates disturbance.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Pittosporum",
        species: "tenuifolium",
        commonName: "dwarf pittosporum",
        growingConditions:
          "Forest-edge conditions, full sun to part-shade, tolerates disturbance."
      }
    },
    {
      image: `${basePath}Echinacea.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Echinacea", genusList),
        species: getShuffledOptions("purpurea", speciesList),
        commonName: getShuffledOptions(
          "Echinacea / Cone Flower",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Full-sun, well-drained soil. Drought tolerant.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Echinacea",
        species: "purpurea",
        commonName: "Echinacea / Cone Flower",
        growingConditions: "Full-sun, well-drained soil. Drought tolerant."
      }
    },
    {
      image: `${basePath}English_Lavender.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Lavendula", genusList),
        species: getShuffledOptions("angustifolia", speciesList),
        commonName: getShuffledOptions("English lavender", commonNameList),
        growingConditions: getShuffledOptions(
          "Full-sun, well-drained alkaline soils, drought tolerant.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Lavendula",
        species: "angustifolia",
        commonName: "English lavender",
        growingConditions:
          "Full-sun, well-drained alkaline soils, drought tolerant."
      }
    },
    {
      image: `${basePath}Fierce_Lancewood_Freox.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Pseudopanax", genusList),
        species: getShuffledOptions("ferox", speciesList),
        commonName: getShuffledOptions("fierce lancewood", commonNameList),
        growingConditions: getShuffledOptions(
          "Forest conditions, full-sun to part-shade, moist, well drained, moist soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Pseudopanax",
        species: "ferox",
        commonName: "fierce lancewood",
        growingConditions:
          "Forest conditions, full-sun to part-shade, moist, well drained, moist soil."
      }
    },
    {
      image: `${basePath}Gaura_So_White.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Gaura", genusList),
        species: getShuffledOptions("lindheimeri", speciesList),
        commonName: getShuffledOptions("Gaura So White", commonNameList),
        growingConditions: getShuffledOptions(
          "Full-sun, well-drained soil. Drought tolerant.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Gaura",
        species: "lindheimeri",
        commonName: "Gaura So White",
        growingConditions: "Full-sun, well-drained soil. Drought tolerant."
      }
    },
    {
      image: `${basePath}Harakeke.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Phormium", genusList),
        species: getShuffledOptions("tenax", speciesList),
        commonName: getShuffledOptions("harakeke / NZ flax", commonNameList),
        growingConditions: getShuffledOptions(
          "Alluvial, wetland and coastal conditions, full sun, tolerant of swampy to dry soils.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Phormium",
        species: "tenax",
        commonName: "harakeke / NZ flax",
        growingConditions:
          "Alluvial, wetland and coastal conditions, full sun, tolerant of swampy to dry soils."
      }
    },
    {
      image: `${basePath}Horopito_Pepper_Tree.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Pseudowintera", genusList),
        species: getShuffledOptions("colorata", speciesList),
        commonName: getShuffledOptions(
          "horopito (or pepper tree)",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Forest conditions, sun/semi shade, well drained, fertile, moist soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Pseudowintera",
        species: "colorata",
        commonName: "horopito (or pepper tree)",
        growingConditions:
          "Forest conditions, sun/semi shade, well drained, fertile, moist soil."
      }
    },
    {
      image: `${basePath}Hunangamoho_Wind_Grass.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Anemanthele", genusList),
        species: getShuffledOptions("lessoniana", speciesList),
        commonName: getShuffledOptions(
          "Hunangāmoho/Wind Grass",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Full-sun / part shade, tolerant of a range of conditions.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Anemanthele",
        species: "lessoniana",
        commonName: "Hunangāmoho/Wind Grass",
        growingConditions:
          "Full-sun / part shade, tolerant of a range of conditions."
      }
    },
    {
      image: `${basePath}Indian_Bean_Tree.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Catalpa", genusList),
        species: getShuffledOptions("bignonioides", speciesList),
        commonName: getShuffledOptions("Indian bean tree", commonNameList),
        growingConditions: getShuffledOptions(
          "Full-sun, moist, well-drained soil. Needs shelter.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Catalpa",
        species: "bignonioides",
        commonName: "Indian bean tree",
        growingConditions: "Full-sun, moist, well-drained soil. Needs shelter."
      }
    },
    {
      image: `${basePath}Kakaha.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Astelia", genusList),
        species: getShuffledOptions("chathamica", speciesList),
        commonName: getShuffledOptions("Kakaha/Silver Spear", commonNameList),
        growingConditions: getShuffledOptions(
          "Coastal conditions, part-shade, shelter from heavy frosts.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Astelia",
        species: "chathamica",
        commonName: "Kakaha/Silver Spear",
        growingConditions:
          "Coastal conditions, part-shade, shelter from heavy frosts."
      }
    },
    {
      image: `${basePath}Kauri.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Agathis", genusList),
        species: getShuffledOptions("australis", speciesList),
        commonName: getShuffledOptions("kauri", commonNameList),
        growingConditions: getShuffledOptions(
          "Forest conditions, full-sun to part-shade, poorly drained, swampy soils.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Agathis",
        species: "australis",
        commonName: "kauri",
        growingConditions:
          "Forest conditions, full-sun to part-shade, poorly drained, swampy soils."
      }
    },
    {
      image: `${basePath}Kohuhu_Black_Matipo.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Pittosporum", genusList),
        species: getShuffledOptions("tenuifolium", speciesList),
        commonName: getShuffledOptions("kohuhu / black matipo", commonNameList),
        growingConditions: getShuffledOptions(
          "Full-sun to part-shade, well drained soils.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Pittosporum",
        species: "tenuifolium",
        commonName: "kohuhu / black matipo",
        growingConditions: "Full-sun to part-shade, well drained soils."
      }
    },
    {
      image: `${basePath}Lambs_Ear.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Stachys", genusList),
        species: getShuffledOptions("byzantina", speciesList),
        commonName: getShuffledOptions("lambs ear", commonNameList),
        growingConditions: getShuffledOptions(
          "Full-sun to part-shade. Drought and cold tolerant.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Stachys",
        species: "byzantina",
        commonName: "lambs ear",
        growingConditions: "Full-sun to part-shade. Drought and cold tolerant."
      }
    },
    {
      image: `${basePath}Lancewood_Crassifolius.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Pseudopanax", genusList),
        species: getShuffledOptions("crassifolius", speciesList),
        commonName: getShuffledOptions("lancewood", commonNameList),
        growingConditions: getShuffledOptions(
          "Forest conditions, full-sun to part-shade, moist, well drained, moist soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Pseudopanax",
        species: "crassifolius",
        commonName: "lancewood",
        growingConditions:
          "Forest conditions, full-sun to part-shade, moist, well drained, moist soil."
      }
    },
    {
      image: `${basePath}Ligularia.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Ligularia", genusList),
        species: getShuffledOptions("dentata", speciesList),
        commonName: getShuffledOptions(
          "Ligularia / Tractor seat Plant",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Forest conditions, part-full shade, moist, well-drained soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Ligularia",
        species: "dentata",
        commonName: "Ligularia / Tractor seat Plant",
        growingConditions:
          "Forest conditions, part-full shade, moist, well-drained soil."
      }
    },
    {
      image: `${basePath}Mahoe.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Melicytus", genusList),
        species: getShuffledOptions("ramiflorus", speciesList),
        commonName: getShuffledOptions("mahoe / whiteywood", commonNameList),
        growingConditions: getShuffledOptions(
          "Forest edge conditions, well drained soil, tolerates disturbance, sun/semi shade",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Melicytus",
        species: "ramiflorus",
        commonName: "mahoe / whiteywood",
        growingConditions:
          "Forest edge conditions, well drained soil, tolerates disturbance, sun/semi shade"
      }
    },
    {
      image: `${basePath}Malborough_Rock_Daisy.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Pachystegia", genusList),
        species: getShuffledOptions("insignis", speciesList),
        commonName: getShuffledOptions(
          "Marlborough rock daisy",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Coastal conditions, full sun, well drained soil",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Pachystegia",
        species: "insignis",
        commonName: "Marlborough rock daisy",
        growingConditions: "Coastal conditions, full sun, well drained soil"
      }
    },
    {
      image: `${basePath}Mingimingi.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Coprosma", genusList),
        species: getShuffledOptions("propinqua", speciesList),
        commonName: getShuffledOptions("mingimingi", commonNameList),
        growingConditions: getShuffledOptions(
          "Grows in a variety of conditions from well drained - wet soils, prefers full sun/part shade.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Coprosma",
        species: "propinqua",
        commonName: "mingimingi",
        growingConditions:
          "Grows in a variety of conditions from well drained - wet soils, prefers full sun/part shade."
      }
    },
    {
      image: `${basePath}Miniature_Toetoe.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Chionochloa", genusList),
        species: getShuffledOptions("flavicans", speciesList),
        commonName: getShuffledOptions("miniature toetoe", commonNameList),
        growingConditions: getShuffledOptions(
          "Coastal and sub-alpine conditions, moist well-drained soils, cold and wind tolerant.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Chionochloa",
        species: "flavicans",
        commonName: "miniature toetoe",
        growingConditions:
          "Coastal and sub-alpine conditions, moist well-drained soils, cold and wind tolerant."
      }
    },
    {
      image: `${basePath}Mountain_Totara.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Podocarpus", genusList),
        species: getShuffledOptions("nivalis", speciesList),
        commonName: getShuffledOptions(
          "Mountain / Snow Totara",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Alpine conditions, full sun, moist, fertile, well drained soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Podocarpus",
        species: "nivalis",
        commonName: "Mountain / Snow Totara",
        growingConditions:
          "Alpine conditions, full sun, moist, fertile, well drained soil."
      }
    },
    {
      image: `${basePath}Mountain_Beech.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Fuscospora", genusList),
        species: getShuffledOptions("cliffortioides", speciesList),
        commonName: getShuffledOptions("mountain beech", commonNameList),
        growingConditions: getShuffledOptions(
          "Alpine conditions, full sun, moist, fertile, well drained soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Fuscospora",
        species: "cliffortioides",
        commonName: "mountain beech",
        growingConditions:
          "Alpine conditions, full sun, moist, fertile, well drained soil."
      }
    },
    {
      image: `${basePath}Nikau_Palm.png`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Rhopalostylis", genusList),
        species: getShuffledOptions("sapida", speciesList),
        commonName: getShuffledOptions("nikau palm", commonNameList),
        growingConditions: getShuffledOptions(
          "Shaded gullies, moist soils, shelter from frost and wind",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Rhopalostylis",
        species: "sapida",
        commonName: "nikau palm",
        growingConditions:
          "Shaded gullies, moist soils, shelter from frost and wind"
      }
    },
    {
      image: `${basePath}Norweigan_Purple_Maple.png`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Acer", genusList),
        species: getShuffledOptions("platanoides", speciesList),
        commonName: getShuffledOptions(
          "Norweigan Purple Maple",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Full sun to part shade, moist, well-drained soils.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Acer",
        species: "platanoides",
        commonName: "Norweigan Purple Maple",
        growingConditions: "Full sun to part shade, moist, well-drained soils."
      }
    },
    {
      image: `${basePath}NZ_Daphne.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Pimelea", genusList),
        species: getShuffledOptions("prostrata subsp. prostrata", speciesList),
        commonName: getShuffledOptions("NZ daphne", commonNameList),
        growingConditions: getShuffledOptions(
          "Coastal to alpine conditions.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Pimelea",
        species: "prostrata subsp. prostrata",
        commonName: "NZ daphne",
        growingConditions: "Coastal to alpine conditions."
      }
    },
    {
      image: `${basePath}NZ_Iris.png`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Libertia", genusList),
        species: getShuffledOptions("peregrinans", speciesList),
        commonName: getShuffledOptions("NZ iris", commonNameList),
        growingConditions: getShuffledOptions(
          "Coastal conditions, full sun, well drained soil",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Libertia",
        species: "peregrinans",
        commonName: "NZ iris",
        growingConditions: "Coastal conditions, full sun, well drained soil"
      }
    },
    {
      image: `${basePath}Oioi.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Apodasmia", genusList),
        species: getShuffledOptions("similis", speciesList),
        commonName: getShuffledOptions(
          "oioi / jointed wire rush",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Wetland conditions, fresh water.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Apodasmia",
        species: "similis",
        commonName: "oioi / jointed wire rush",
        growingConditions: "Wetland conditions, fresh water."
      }
    },
    {
      image: `${basePath}Panakenake_Pratia.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Pratia (syn. Lobelia)", genusList),
        species: getShuffledOptions("angulata", speciesList),
        commonName: getShuffledOptions("panakenake", commonNameList),
        growingConditions: getShuffledOptions(
          "Part-shade, moist soil. Tolerates light disturbance.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Pratia (syn. Lobelia)",
        species: "angulata",
        commonName: "panakenake",
        growingConditions:
          "Part-shade, moist soil. Tolerates light disturbance."
      }
    },
    {
      image: `${basePath}Penstemon.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Penstemon", genusList),
        species: getShuffledOptions("scrophulariaceae", speciesList),
        commonName: getShuffledOptions("Penstemon", commonNameList),
        growingConditions: getShuffledOptions(
          "Well drained soil. Drought and humidity tolerant.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Penstemon",
        species: "scrophulariaceae",
        commonName: "Penstemon",
        growingConditions: "Well drained soil. Drought and humidity tolerant."
      }
    },
    {
      image: `${basePath}Poroporo.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Solanum", genusList),
        species: getShuffledOptions("laciniatum", speciesList),
        commonName: getShuffledOptions("poroporo", commonNameList),
        growingConditions: getShuffledOptions(
          "Coastal to montane conditions. Preference for disturbed sites.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Solanum",
        species: "laciniatum",
        commonName: "poroporo",
        growingConditions:
          "Coastal to montane conditions. Preference for disturbed sites."
      }
    },
    {
      image: `${basePath}Red_Beech.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Fuscospora", genusList),
        species: getShuffledOptions("fusca", speciesList),
        commonName: getShuffledOptions("red beech", commonNameList),
        growingConditions: getShuffledOptions(
          "Forest conditions, full-sun to part-shade, moist, well drained, moist soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Fuscospora",
        species: "fusca",
        commonName: "red beech",
        growingConditions:
          "Forest conditions, full-sun to part-shade, moist, well drained, moist soil."
      }
    },
    {
      image: `${basePath}Red_Coprosma.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Coprosma", genusList),
        species: getShuffledOptions("rugosa", speciesList),
        commonName: getShuffledOptions("red coprosma", commonNameList),
        growingConditions: getShuffledOptions(
          "Lowland to montane conditions, full-sun, dry to moist, well drained soils.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Coprosma",
        species: "rugosa",
        commonName: "red coprosma",
        growingConditions:
          "Lowland to montane conditions, full-sun, dry to moist, well drained soils."
      }
    },
    {
      image: `${basePath}Rengarenga.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Arthropodium", genusList),
        species: getShuffledOptions("cirratum", speciesList),
        commonName: getShuffledOptions(
          "Rengarenga / Rock Lily",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Coastal conditions, full-sun to full-shade, dry-to-moist soils.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Arthropodium",
        species: "cirratum",
        commonName: "Rengarenga / Rock Lily",
        growingConditions:
          "Coastal conditions, full-sun to full-shade, dry-to-moist soils."
      }
    },
    {
      image: `${basePath}Rimu.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Dacrydium", genusList),
        species: getShuffledOptions("cupressinum", speciesList),
        commonName: getShuffledOptions("rimu", commonNameList),
        growingConditions: getShuffledOptions(
          "Full sun, well drained soil/ dry.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Dacrydium",
        species: "cupressinum",
        commonName: "rimu",
        growingConditions: "Full sun, well drained soil/ dry."
      }
    },
    {
      image: `${basePath}Sceranthus.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Sceranthus", genusList),
        species: getShuffledOptions("biflorus", speciesList),
        commonName: getShuffledOptions("Sceranthus", commonNameList),
        growingConditions: getShuffledOptions(
          "Coastal and rocky conditions, full-part shade, moist, well-drained soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Sceranthus",
        species: "biflorus",
        commonName: "Sceranthus",
        growingConditions:
          "Coastal and rocky conditions, full-part shade, moist, well-drained soil."
      }
    },
    {
      image: `${basePath}Sedum_Midnight_Coral.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Sedum", genusList),
        species: getShuffledOptions("spectabile", speciesList),
        commonName: getShuffledOptions("Sedum", commonNameList),
        growingConditions: getShuffledOptions(
          "Full-sun to part-shade. Heat and drought tolerant.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Sedum",
        species: "spectabile",
        commonName: "Sedum",
        growingConditions: "Full-sun to part-shade. Heat and drought tolerant."
      }
    },
    {
      image: `${basePath}Waiuatua_Shore_Spurge.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Euphorbia", genusList),
        species: getShuffledOptions("glauca", speciesList),
        commonName: getShuffledOptions(
          "shore spurge (or waiu-atua)",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Coastal conditions, full sun, well drained soil",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Euphorbia",
        species: "glauca",
        commonName: "shore spurge (or waiu-atua)",
        growingConditions: "Coastal conditions, full sun, well drained soil"
      }
    },
    {
      image: `${basePath}Silver_Birch.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Betula", genusList),
        species: getShuffledOptions("pendula", speciesList),
        commonName: getShuffledOptions("silver birch", commonNameList),
        growingConditions: getShuffledOptions(
          "Full sun to part shade, moist, well-drained soils.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Betula",
        species: "pendula",
        commonName: "silver birch",
        growingConditions: "Full sun to part shade, moist, well-drained soils."
      }
    },
    {
      image: `${basePath}Silver_tussok.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Poa", genusList),
        species: getShuffledOptions("cita", speciesList),
        commonName: getShuffledOptions("silver tussock", commonNameList),
        growingConditions: getShuffledOptions(
          "Coastal to alpine. Well drained soil, full sun.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Poa",
        species: "cita",
        commonName: "silver tussock",
        growingConditions: "Coastal to alpine. Well drained soil, full sun."
      }
    },
    {
      image: `${basePath}Teucridium.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Teucridium", genusList),
        species: getShuffledOptions("parvifolium", speciesList),
        commonName: getShuffledOptions("Teucridium", commonNameList),
        growingConditions: getShuffledOptions(
          "Alluvial conditions, full-sun to part-shade. Tolerates poor, dry soils.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Teucridium",
        species: "parvifolium",
        commonName: "Teucridium",
        growingConditions:
          "Alluvial conditions, full-sun to part-shade. Tolerates poor, dry soils."
      }
    },
    {
      image: `${basePath}Ti_Kouka_Cabbage_Tree.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Cordyline", genusList),
        species: getShuffledOptions("australis", speciesList),
        commonName: getShuffledOptions(
          "Tī Kōuka / cabbage tree",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Wetland to scrubland conditions, full-sun, drought-tolerant, does not tolerate shade.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Cordyline",
        species: "australis",
        commonName: "Tī Kōuka / cabbage tree",
        growingConditions:
          "Wetland to scrubland conditions, full-sun, drought-tolerant, does not tolerate shade."
      }
    },
    {
      image: `${basePath}Toatoa_Fireweed.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Haloregis", genusList),
        species: getShuffledOptions("erecta", speciesList),
        commonName: getShuffledOptions("toatoa / fireweed", commonNameList),
        growingConditions: getShuffledOptions(
          "Coastal to montane conditions. Colonises disturbed sites such as forest margins and floodplains.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Haloregis",
        species: "erecta",
        commonName: "toatoa / fireweed",
        growingConditions:
          "Coastal to montane conditions. Colonises disturbed sites such as forest margins and floodplains."
      }
    },
    {
      image: `${basePath}Turutu.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Dianella", genusList),
        species: getShuffledOptions("nigra", speciesList),
        commonName: getShuffledOptions("turutu", commonNameList),
        growingConditions: getShuffledOptions(
          "Forest conditions, sun/semi shade, well drained, fertile, moist soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Dianella",
        species: "nigra",
        commonName: "turutu",
        growingConditions:
          "Forest conditions, sun/semi shade, well drained, fertile, moist soil."
      }
    },
    {
      image: `${basePath}Weeping_Broom.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Carmichaelia", genusList),
        species: getShuffledOptions("stevensonii", speciesList),
        commonName: getShuffledOptions("weeping broom", commonNameList),
        growingConditions: getShuffledOptions(
          "Alpine / alluvial conditions, full sun, moist, well drained soil.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Carmichaelia",
        species: "stevensonii",
        commonName: "weeping broom",
        growingConditions:
          "Alpine / alluvial conditions, full sun, moist, well drained soil."
      }
    },
    {
      image: `${basePath}Weeping_Kowhai_Small_Leaved_Kowhai.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Sophora", genusList),
        species: getShuffledOptions("microphylla", speciesList),
        commonName: getShuffledOptions(
          "weeping kowhai / small leaved kowhai",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Most soil types if well drained, full sun/part shade.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Sophora",
        species: "microphylla",
        commonName: "weeping kowhai / small leaved kowhai",
        growingConditions:
          "Most soil types if well drained, full sun/part shade."
      }
    },
    {
      image: `${basePath}Wharariki_Mountain_Flax.jpg`,
      question: "Name that Plant!",
      options: {
        genus: getShuffledOptions("Phormium", genusList),
        species: getShuffledOptions("cookianum", speciesList),
        commonName: getShuffledOptions(
          "wharariki / mountain flax",
          commonNameList
        ),
        growingConditions: getShuffledOptions(
          "Coastal and alpine conditions. Tolerant of dry, cold and exposed conditions.",
          growingConditionsList
        )
      },
      correctAnswers: {
        genus: "Phormium",
        species: "cookianum",
        commonName: "wharariki / mountain flax",
        growingConditions:
          "Coastal and alpine conditions. Tolerant of dry, cold and exposed conditions."
      }
    }
  ];

const quizContainer = document.getElementById("quiz");
const resultsContainer = document.getElementById("results");
const submitButton = document.getElementById("submit");
const previousButton = document.getElementById("previous");
const nextButton = document.getElementById("next");

let numCorrect = 0;
let shuffledSlides = [...quizData]; // Clone quiz data for shuffling
let seenSlides = []; // Track visited slides

// Shuffle quiz slides at the start
function shuffleArray(array) {
    for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
    }
}
shuffleArray(shuffledSlides);

function buildQuiz() {
    const output = [];

    quizData.forEach((currentQuestion, questionNumber) => {
        const options = [];

        for (let key in currentQuestion.options) {
            shuffleArray(currentQuestion.options[key]);

            const questionText = {
                genus: "What is the Genus?",
                species: "What is the species?",
                commonName: "What is its common name?",
                growingConditions: "What are its preferred growing conditions?"
            };

            options.push(
                `<div class="question">${questionText[key]}</div>
                <div class="answers">
                    ${currentQuestion.options[key]
                        .map((option) => {
                            return `
                                <label>
                                    <input type="radio" name="question${questionNumber}${key}" value="${option}">
                                    ${option}
                                </label>
                            `;
                        })
                        .join("")}
                </div>`
            );
        }

        output.push(
            `<div class="slide" data-slide-index="${questionNumber}">
                <div class="image"><img src="${currentQuestion.image}" alt="Plant Image"></div>
                <div class="question">${currentQuestion.question}</div>
                ${options.join("")}
                <div class="score-display">Score: 0 / 4</div>
            </div>`
        );
    });

    quizContainer.innerHTML = output.join("");
}

function showSlide(n) {
    const slides = document.querySelectorAll(".slide");
    slides.forEach(slide => slide.classList.remove("active-slide"));
    slides[n].classList.add("active-slide");
}

function showNextSlide() {
    if (shuffledSlides.length === 0) {
        console.log("All slides have been visited.");
        return;
    }
    
    let nextSlide = shuffledSlides.shift();
    seenSlides.push(nextSlide);

    let nextIndex = quizData.indexOf(nextSlide);
    showSlide(nextIndex);
}

function showPreviousSlide() {
    if (seenSlides.length <= 1) return;
    
    let lastSeen = seenSlides.pop();
    shuffledSlides.unshift(lastSeen);

    let prevIndex = quizData.indexOf(seenSlides[seenSlides.length - 1]);
    showSlide(prevIndex);
}

function showResults() {
    numCorrect = 0;
    const answerContainers = quizContainer.querySelectorAll(".answers");
    quizData.forEach((currentQuestion, questionNumber) => {
        for (let key in currentQuestion.correctAnswers) {
            const selector = `input[name=question${questionNumber}${key}]:checked`;
            const userAnswer = (quizContainer.querySelector(selector) || {}).value;
            const correctAnswer = currentQuestion.correctAnswers[key];

            if (userAnswer === correctAnswer) {
                numCorrect++;
                answerContainers[questionNumber]
                    .querySelector(`input[value="${correctAnswer}"]`)
                    .parentElement.classList.add("correct");
            } else {
                answerContainers[questionNumber]
                    .querySelector(`input[value="${userAnswer}"]`)
                    .parentElement.classList.add("incorrect");
                answerContainers[questionNumber]
                    .querySelector(`input[value="${correctAnswer}"]`)
                    .parentElement.classList.add("correct");
            }
        }
    });

    resultsContainer.innerHTML = `You got ${numCorrect} out of ${quizData.length * 4} correct`;
}

submitButton.addEventListener("click", showResults);
nextButton.addEventListener("click", showNextSlide);
previousButton.addEventListener("click", showPreviousSlide);

  // Build the quiz, attach listeners, and show the first slide
  buildQuiz();
showNextSlide();
});