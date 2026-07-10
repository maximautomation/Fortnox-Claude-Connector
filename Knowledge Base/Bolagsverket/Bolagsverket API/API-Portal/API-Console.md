---
title: "[Devportal] Företagsinformation- WSO2 APIM"
source: "https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/api-console"
author:
published:
created: 2026-07-09
description:
tags:
  - "clippings"
---
### Notice

You need an access token to try the API. Please log in and subscribe to the API to generate an access token. If you already have an access token, please provide it below.

Servers

### organisationsinformationAPI to retrieve data about companies, persons, signatory power and cases.

With this operation you can retrieve data about a company.

#### Parameters

| Name | Description |
| --- | --- |
| X-Request-Id  string  (header) | Client generated ID to call the API. In case of error this will be sent in the attribute `requestId` or as a header attribute.  *Example*: d120654c-0d09-481a-8956-940a76474e6b |

#### Request body

An object to specify `identitetsbeteckning` (company registration number) and if needed `namnskyddslopnummer` (used to separate companies for organisation types that can have more than one company on the same company registration number) and fields to specify the information objects you want in the answer. Possible information objects are `ORGANISATIONSADRESSER` (postal address and email address), `FIRMATECKNING` (signatory power), `FUNKTIONARER` (company officers), `HEMVISTKOMMUN` (domicile for the company), `RAKENSKAPSAR` (financial year), `ORGANISATIONSDATUM` (different dates regarding the company), `VERKSAMHETSBESKRIVNING` (description of the business activities), `AKTIEINFORMATION` (information about stocks in the company), `SAMTLIGA_ORGANISATIONSNAMN` (all business names including business names in translation and secondary business names), `ORGANISATIONSENGAGEMANG` (showing a company's assignments in other companies, `TILLSTAND` (showing a company's permits), `OVRIG_ORGANISATIONSINFORMATION` (other organisation information), `ORGANISATIONSMARKERINGAR` (markings on the company), `BESTAMMELSER` (regulations for the company), `VAKANSER_OCH_UPPLYSNINGAR` (vacancies and other information about the company), `EKONOMISK_PLAN` (financial plan for the company form BRF), `UTLANDSK_FILIALAGANDE_ORGANISATION` (information about a foreign company having a Swedish branch), `FINANSIELLA_RAPPORTER` (information about a company's financial reports), and an optional timestamp ('tidpunkt') to retrieve historical information about the company, `DETALJERAD_STATUS` (Detailed status of a company), `UTLANDSKA_FILIALER` (Foreign branches of a company)

- Example Value
- Schema

```json
{
  "identitetsbeteckning": "string",
  "namnskyddslopnummer": "1",
  "arendenummer": "string",
  "organisationInformationsmangd": [
    "AKTIEINFORMATION"
  ],
  "tidpunkt": "string"
}
```

#### Responses

CodeDescriptionLinks200

Reply with requested company data.

Media type Controls `Accept` header.

- Example Value
- Schema

```json
[
  {
    "identitet": {
      "typ": {
        "kod": "string",
        "klartext": "string"
      },
      "identitetsbeteckning": "string"
    },
    "namnskyddslopnummer": 2,
    "arende": {
      "arendenummer": "1234/2024",
      "avslutatTidpunkt": "2000-01-01T00:00:00.000+02:00"
    },
    "organisationsnamn": {
      "typ": {
        "kod": "string",
        "klartext": "string"
      },
      "namn": "string"
    },
    "organisationsform": {
      "kod": "string",
      "klartext": "string"
    },
    "organisationsstatusar": [
      {
        "kod": "string",
        "klartext": "string",
        "typ": "string",
        "datum": "2026-07-09"
      }
    ],
    "organisationsdatum": {
      "registreringsdatum": "2026-07-09",
      "bildatDatum": "2026-07-09"
    },
    "hemvistkommun": {
      "typ": "string",
      "lanForHemvistkommun": {
        "kod": "string",
        "klartext": "string"
      },
      "kommun": {
        "kod": "string",
        "klartext": "string"
      }
    },
    "rakenskapsar": {
      "rakenskapsarInleds": "string",
      "rakenskapsarAvslutas": "string"
    },
    "verksamhetsbeskrivning": "string",
    "organisationsadresser": {
      "postadress": {
        "coAdress": "string",
        "adress": "string",
        "postnummer": "string",
        "postort": "string",
        "adressrad1": "string",
        "adressrad2": "string",
        "land": {
          "kod": "string",
          "klartext": "string"
        }
      },
      "epostadress": "string"
    },
    "firmateckning": {
      "kodad": [
        [
          {
            "typ": {
              "kod": "string",
              "klartext": "string"
            },
            "ordning": 1,
            "funktionarsroller": [
              {
                "kod": "string",
                "klartext": "string"
              }
            ],
            "funktionarer": [
              {
                "personnamn": {
                  "fornamn": "string",
                  "efternamn": "string"
                },
                "organisationsnamn": {
                  "typ": {
                    "kod": "string",
                    "klartext": "string"
                  },
                  "namn": "string"
                },
                "identitet": {
                  "typ": {
                    "kod": "string",
                    "klartext": "string"
                  },
                  "identitetsbeteckning": "string"
                }
              }
            ]
          }
        ]
      ],
      "klartext": "string",
      "prokuratext": "string"
    },
    "samtligaOrganisationsnamn": [
      {
        "typ": {
          "kod": "string",
          "klartext": "string"
        },
        "namn": "string",
        "registreringsdatum": "2026-07-09",
        "verksamhetsbeskrivningSarskiltForetagsnamn": "string",
        "beslutAvStamma": true,
        "iBestammelser": true,
        "registreringslan": {
          "kod": "string",
          "klartext": "string"
        },
        "registreringFlerLan": [
          {
            "kod": "string",
            "klartext": "string"
          }
        ]
      }
    ],
    "funktionarer": [
      {
        "personnamn": {
          "fornamn": "string",
          "efternamn": "string"
        },
        "organisationsnamn": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "namn": "string"
        },
        "identitet": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "identitetsbeteckning": "string"
        },
        "funktionarsroller": [
          {
            "kod": "string",
            "klartext": "string"
          }
        ],
        "utlandskBosattning": {
          "kod": "string",
          "klartext": "string"
        },
        "dispensbosattning": {
          "tillsVidare": true,
          "tomDatum": "2024-12-31"
        },
        "postadress": {
          "coAdress": "string",
          "adress": "string",
          "postnummer": "string",
          "postort": "string",
          "adressrad1": "string",
          "adressrad2": "string",
          "land": {
            "kod": "string",
            "klartext": "string"
          }
        },
        "representerasAv": {
          "personnamn": {
            "fornamn": "string",
            "efternamn": "string"
          },
          "identitet": {
            "typ": {
              "kod": "string",
              "klartext": "string"
            },
            "identitetsbeteckning": "string"
          }
        },
        "insats": "string",
        "anteckning": "string"
      }
    ],
    "antalValdaFunktionarer": {
      "ledamoter": 0,
      "suppleanter": 0
    },
    "aktieinformation": {
      "aktiekapital": {
        "belopp": 12000,
        "valuta": "SEK"
      },
      "antalAktier": 1200,
      "aktiegranser": {
        "aktiekapitalGranser": {
          "lagst": 25000,
          "hogst": 100000
        },
        "antalAktierGranser": {
          "lagst": 1000,
          "hogst": 10000
        },
        "valuta": "SEK"
      },
      "aktieslag": [
        {
          "namn": "A",
          "antal": 1000,
          "aktieslagGranser": {
            "lagst": 1000,
            "hogst": 10000
          },
          "rostvarde": "1"
        }
      ],
      "fritext": "Antalet aktier av respektive slag får motsvara högst hela antalet aktier i bolaget.",
      "kvotvarde": {
        "belopp": 12000,
        "valuta": "SEK"
      },
      "nedsattningPagar": true
    },
    "organisationsengagemang": [
      {
        "organisation": {
          "identitet": {
            "typ": {
              "kod": "string",
              "klartext": "string"
            },
            "identitetsbeteckning": "string"
          },
          "namnskyddslopnummer": 2,
          "personnamn": {
            "fornamn": "string",
            "efternamn": "string"
          },
          "organisationsnamn": {
            "typ": {
              "kod": "string",
              "klartext": "string"
            },
            "namn": "string"
          },
          "organisationsform": {
            "kod": "string",
            "klartext": "string"
          },
          "organisationsstatusar": [
            {
              "kod": "string",
              "klartext": "string",
              "typ": "string",
              "datum": "2026-07-09"
            }
          ]
        },
        "funktionar": {
          "personnamn": {
            "fornamn": "string",
            "efternamn": "string"
          },
          "organisationsnamn": {
            "typ": {
              "kod": "string",
              "klartext": "string"
            },
            "namn": "string"
          },
          "identitet": {
            "typ": {
              "kod": "string",
              "klartext": "string"
            },
            "identitetsbeteckning": "string"
          },
          "funktionarsroller": [
            {
              "kod": "string",
              "klartext": "string"
            }
          ],
          "utlandskBosattning": {
            "kod": "string",
            "klartext": "string"
          },
          "dispensbosattning": {
            "tillsVidare": true,
            "tomDatum": "2024-12-31"
          },
          "postadress": {
            "coAdress": "string",
            "adress": "string",
            "postnummer": "string",
            "postort": "string",
            "adressrad1": "string",
            "adressrad2": "string",
            "land": {
              "kod": "string",
              "klartext": "string"
            }
          },
          "representerasAv": {
            "personnamn": {
              "fornamn": "string",
              "efternamn": "string"
            },
            "identitet": {
              "typ": {
                "kod": "string",
                "klartext": "string"
              },
              "identitetsbeteckning": "string"
            }
          },
          "insats": "string",
          "anteckning": "string"
        }
      }
    ],
    "tillstand": {
      "typ": {
        "kod": "string",
        "klartext": "string"
      },
      "datum": "2026-07-09",
      "aterkallatDatum": "2026-07-09",
      "forlangtDatum": "2026-07-09",
      "forverkatDatum": "2026-07-09"
    },
    "ovrigOrganisationinformation": {
      "externaAnteckningar": "string",
      "ovrigaRegisteruppgifter": "string"
    },
    "organisationsmarkeringar": [
      {
        "kod": "string",
        "klartext": "string"
      }
    ],
    "bestammelser": {
      "typ": {
        "kod": "string",
        "klartext": "string"
      },
      "godkannandeKravs": true,
      "kungorelsedatum": "2026-07-09",
      "registreringsdatum": "2026-07-09",
      "antagetDatum": "2026-07-09",
      "kallelsesatt": "string",
      "godkandAvInstanser": [
        {
          "datum": "2026-07-09",
          "kommunfullmaktigeI": {
            "kod": "string",
            "klartext": "string"
          },
          "instans": {
            "kod": "string",
            "klartext": "string"
          },
          "fritext": "string"
        }
      ],
      "styrelsegranser": {
        "ledamoter": {
          "lagst": 1000,
          "hogst": 10000
        },
        "suppleanter": {
          "lagst": 1000,
          "hogst": 10000
        }
      },
      "stammotidManader": [
        "string"
      ],
      "stammotidSenastManad": "string",
      "stammotidInomSexManader": true,
      "frivilligaBestammelser": [
        {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "datum": "2026-07-09"
        }
      ],
      "fritext": "string"
    },
    "vakanserOchUpplysningar": {
      "vakansOchUpplysning": [
        {
          "typ": {
            "kod": "string",
            "klartext": "string",
            "typ": "string",
            "datum": "2026-07-09"
          }
        }
      ],
      "fritext": "string"
    },
    "ekonomiskPlan": {
      "registreradDatum": "2026-07-09",
      "senastRegistreradDatum": "2026-07-09",
      "forenkladRegistreradDatum": "2026-07-09"
    },
    "utlandskFilialagandeOrganisation": {
      "identitet": {
        "typ": {
          "kod": "string",
          "klartext": "string"
        },
        "identitetsbeteckning": "string"
      },
      "angivetEuid": "string",
      "organisationsnamn": {
        "typ": {
          "kod": "string",
          "klartext": "string"
        },
        "namn": "string"
      },
      "registreringsdatum": "2026-07-09",
      "verksamhetsbeskrivning": "string",
      "sate": "string",
      "postadress": {
        "coAdress": "string",
        "adress": "string",
        "postnummer": "string",
        "postort": "string",
        "adressrad1": "string",
        "adressrad2": "string",
        "land": {
          "kod": "string",
          "klartext": "string"
        }
      },
      "rakenskapsar": {
        "rakenskapsarInleds": "string",
        "rakenskapsarAvslutas": "string"
      },
      "ejVerifieratOrganisationsregister": {
        "organisationsregister": "string",
        "land": {
          "kod": "string",
          "klartext": "string"
        }
      },
      "aktieinformation": {
        "belopp": 0,
        "valuta": {
          "kod": "string",
          "klartext": "string"
        },
        "inbetaltBelopp": 0
      },
      "funktionarer": [
        {
          "namn": "string",
          "idnummer": "string",
          "postadress": {
            "coAdress": "string",
            "adress": "string",
            "postnummer": "string",
            "postort": "string",
            "adressrad1": "string",
            "adressrad2": "string",
            "land": {
              "kod": "string",
              "klartext": "string"
            }
          },
          "funktion": "string"
        }
      ]
    },
    "finansiellaRapporter": [
      {
        "arende": {
          "arendenummer": "string",
          "avslutatTidpunkt": "string"
        },
        "rapporter": [
          {
            "rapporteringsperiod": {
              "periodFrom": "string",
              "periodTom": "string"
            },
            "rapportTyp": {
              "kod": "string",
              "klartext": "string"
            },
            "ankomDatum": "string",
            "handlaggningAvslutadDatum": "string",
            "registreradDatum": "string",
            "bolagsstammansForlangningDatum": "string",
            "innehallerKoncernredovisning": true,
            "vinstutdelning": {
              "beslutadDatum": "string",
              "valuta": {
                "kod": "string",
                "klartext": "string"
              },
              "belopp": 0
            }
          }
        ]
      }
    ],
    "detaljeradStatus": {
      "avregistreradOrganisation": {
        "avregistreringsdatum": "string",
        "arendenummer": "string",
        "avregistreringsorsak": {
          "kod": "string",
          "klartext": "string"
        },
        "anteckning": "string"
      },
      "avvecklingsEllerOmstruktureringsforfaranden": [
        {
          "anmalFordringarSenastDatum": "string",
          "avvecklingsEllerOmstruktureringsforfarandehandelse": {
            "avslutadDatum": "string",
            "avvecklingsEllerOmstruktureringsforfarandehandelsetyp": {
              "kod": "string",
              "klartext": "string"
            },
            "beslutAvInstans": {
              "svenskBeslutsfattare": {
                "instans": {
                  "kod": "string",
                  "klartext": "string"
                },
                "instanstyp": {
                  "kod": "string",
                  "klartext": "string"
                }
              },
              "utlandskBeslutsfattare": {
                "land": {
                  "kod": "string",
                  "klartext": "string"
                },
                "namn": "string"
              }
            },
            "beslutsdatum": "string",
            "fortsatterDatum": "string",
            "inleddDatum": "string",
            "malnummer": "string"
          },
          "avvecklingsEllerOmstruktureringsforfarandetyp": {
            "kod": "string",
            "klartext": "string"
          },
          "funktionarIAvvecklingsEllerOmstruktureringsforfarande": {
            "epostadress": "string",
            "funktionarIAvvecklingsEllerOmstruktureringsforfarandetyp": {
              "kod": "string",
              "klartext": "string"
            },
            "personnamn": {
              "fornamn": "string",
              "efternamn": "string"
            },
            "postadress": {
              "coAdress": "string",
              "adress": "string",
              "postnummer": "string",
              "postort": "string",
              "adressrad1": "string",
              "adressrad2": "string",
              "land": {
                "kod": "string",
                "klartext": "string"
              }
            }
          },
          "galdenar": {
            "postadress": {
              "coAdress": "string",
              "adress": "string",
              "postnummer": "string",
              "postort": "string",
              "adressrad1": "string",
              "adressrad2": "string",
              "land": {
                "kod": "string",
                "klartext": "string"
              }
            }
          },
          "insolvensbestammelsetyper": [
            {
              "kod": "string",
              "klartext": "string"
            }
          ],
          "overklagan": {
            "overklaganSenastDatum": "string",
            "overklaganTill": {
              "svenskBeslutsfattare": {
                "instans": {
                  "kod": "string",
                  "klartext": "string"
                }
              },
              "utlandskBeslutsfattare": {
                "land": {
                  "kod": "string",
                  "klartext": "string"
                },
                "namn": "string"
              }
            }
          },
          "underTillsynAv": {
            "instans": {
              "kod": "string",
              "klartext": "string"
            },
            "postadress": {
              "coAdress": "string",
              "adress": "string",
              "postnummer": "string",
              "postort": "string",
              "adressrad1": "string",
              "adressrad2": "string",
              "land": {
                "kod": "string",
                "klartext": "string"
              }
            }
          },
          "verkstallsAv": {
            "instans": {
              "kod": "string",
              "klartext": "string"
            },
            "lagakraftDatum": "string"
          }
        }
      ],
      "fusionsDelningsEllerOmbildningsforfaranden": [
        {
          "rollIForfarandet": "OVERTAGANDE",
          "antalNybildningar": 0,
          "anteckning": "string",
          "arendenummer": [
            "string"
          ],
          "fusionsDelningsEllerOmbildningsforfarandehandelse": {
            "ansokanOmTillstandSenastDatum": "string",
            "atergangenDatum": "string",
            "beslutsdatum": "string",
            "bestridesSenastDatum": "string",
            "forfallenDatum": "string",
            "genomfordDatum": "string",
            "inleddDatum": "string",
            "kallelseBorgenarer": true,
            "kallelseBorgenarerDatum": "string",
            "kungorelsedatum": "string",
            "tillstandBeviljatDatum": "string",
            "vilandeTillOchMedDatum": "string",
            "fusionsDelningsEllerOmbildningsforfarandehandelsetyp": {
              "kod": "string",
              "klartext": "string"
            }
          },
          "fusionsDelningsEllerOmbildningsforfarandetyp": {
            "kod": "string",
            "klartext": "string"
          },
          "kallelse": {
            "kallelsetyp": {
              "kod": "string",
              "klartext": "string"
            }
          },
          "overlamnadDomstol": {
            "overlamnadDatum": "string",
            "registreringsdatum": "string"
          },
          "overlatandeOrganisationer": [
            {
              "svenskOrganisation": {
                "identitetsbeteckning": "string",
                "namn": "string"
              },
              "utlandskOrganisation": {
                "angivetEuid": "string",
                "associationsform": "string",
                "ejVerifieratOrganisationsregister": {
                  "organisationsregister": "string",
                  "land": {
                    "kod": "string",
                    "klartext": "string"
                  }
                },
                "epostadress": "string",
                "identitet": {
                  "typ": {
                    "kod": "string",
                    "klartext": "string"
                  },
                  "identitetsbeteckning": "string"
                },
                "organisationsnamn": {
                  "typ": {
                    "kod": "string",
                    "klartext": "string"
                  },
                  "namn": "string"
                },
                "postadress": {
                  "adressrad1": "string",
                  "adressrad2": "string",
                  "land": {
                    "kod": "string",
                    "klartext": "string"
                  }
                },
                "sate": "string"
              }
            }
          ],
          "overtagandeOrganisationer": [
            {
              "svenskOrganisation": {
                "identitetsbeteckning": "string",
                "namn": "string"
              },
              "utlandskOrganisation": {
                "angivetEuid": "string",
                "associationsform": "string",
                "ejVerifieratOrganisationsregister": {
                  "organisationsregister": "string",
                  "land": {
                    "kod": "string",
                    "klartext": "string"
                  }
                },
                "epostadress": "string",
                "identitet": {
                  "typ": {
                    "kod": "string",
                    "klartext": "string"
                  },
                  "identitetsbeteckning": "string"
                },
                "organisationsnamn": {
                  "typ": {
                    "kod": "string",
                    "klartext": "string"
                  },
                  "namn": "string"
                },
                "postadress": {
                  "adressrad1": "string",
                  "adressrad2": "string",
                  "land": {
                    "kod": "string",
                    "klartext": "string"
                  }
                },
                "sate": "string"
              }
            }
          ],
          "planEllerAvtal": {
            "planEllerAvtalstyp": {
              "kod": "string",
              "klartext": "string"
            }
          },
          "tillstand": {
            "instans": {
              "kod": "string",
              "klartext": "string"
            },
            "instanstyp": {
              "kod": "string",
              "klartext": "string"
            }
          },
          "verkstallsAv": {
            "instans": {
              "kod": "string",
              "klartext": "string"
            },
            "instanstyp": {
              "kod": "string",
              "klartext": "string"
            }
          }
        }
      ]
    },
    "utlandskaFilialer": [
      {
        "registreringsdatum": "2026-07-09",
        "registreringGallerFrom": "2026-07-09",
        "andringsdatum": "2026-07-09",
        "andringGallerFrom": "2026-07-09",
        "avregistreringsdatum": "2026-07-09",
        "avregistreringGallerFrom": "2026-07-09",
        "angivetEuid": "string",
        "organisationsnamn": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "namn": "string"
        },
        "postadress": {
          "adressrad1": "string",
          "adressrad2": "string",
          "adressrad3": "string",
          "postnummerOrt": {
            "postort": "string",
            "postnummer": "string"
          },
          "land": {
            "kod": "string",
            "klartext": "string"
          }
        },
        "ejVerifieratOrganisationsregister": {
          "organisationsregister": "string",
          "land": {
            "kod": "string",
            "klartext": "string"
          }
        }
      }
    ]
  }
]
```

*No links*400

Wrong format on identifier.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*401

Wrong access token.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | Identification of the API-call | string |

*No links*403

Forbidden call, check the scope.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | ID on the call | string |

*No links*404

Personal data or company data is missing.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*default

Unexpected error

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*

With this operation you can retrieve data about a person.

#### Parameters

| Name | Description |
| --- | --- |
| X-Request-Id  string  (header) | Client generated ID to call the API. In case of error this will be sent in the attribute `requestId` or as a header attribute.  *Example*: d120654c-0d09-481a-8956-940a76474e6b |

#### Request body

An object to specify `identitetsbeteckning` (personal identity number) and fields to specify the information objects you want in the answer. Possible information objects are `ORGANISATIONSENGAGEMANG` (Showing a person’s assignments in companies), `PERSONLIG_KONKURS` (personal bankruptcy), `BITRADESFORBUD` (prohibition of financial assistance), `NARINGSFORBUD` (trade ban (prohibition to carry on business)).

- Example Value
- Schema

```json
{
  "identitetsbeteckning": "string",
  "personInformationsmangd": [
    "ORGANISATIONSENGAGEMANG"
  ]
}
```

#### Responses

CodeDescriptionLinks200

Reply with requested personal data.

Media type Controls `Accept` header.

- Example Value
- Schema

```json
{
  "identitet": {
    "typ": {
      "kod": "string",
      "klartext": "string"
    },
    "identitetsbeteckning": "string"
  },
  "personnamn": {
    "fornamn": "string",
    "efternamn": "string"
  },
  "organisationsengagemang": [
    {
      "organisation": {
        "identitet": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "identitetsbeteckning": "string"
        },
        "namnskyddslopnummer": 2,
        "personnamn": {
          "fornamn": "string",
          "efternamn": "string"
        },
        "organisationsnamn": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "namn": "string"
        },
        "organisationsform": {
          "kod": "string",
          "klartext": "string"
        },
        "organisationsstatusar": [
          {
            "kod": "string",
            "klartext": "string",
            "typ": "string",
            "datum": "2026-07-09"
          }
        ]
      },
      "funktionar": {
        "personnamn": {
          "fornamn": "string",
          "efternamn": "string"
        },
        "organisationsnamn": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "namn": "string"
        },
        "identitet": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "identitetsbeteckning": "string"
        },
        "funktionarsroller": [
          {
            "kod": "string",
            "klartext": "string"
          }
        ],
        "utlandskBosattning": {
          "kod": "string",
          "klartext": "string"
        },
        "dispensbosattning": {
          "tillsVidare": true,
          "tomDatum": "2024-12-31"
        },
        "postadress": {
          "coAdress": "string",
          "adress": "string",
          "postnummer": "string",
          "postort": "string",
          "adressrad1": "string",
          "adressrad2": "string",
          "land": {
            "kod": "string",
            "klartext": "string"
          }
        },
        "representerasAv": {
          "personnamn": {
            "fornamn": "string",
            "efternamn": "string"
          },
          "identitet": {
            "typ": {
              "kod": "string",
              "klartext": "string"
            },
            "identitetsbeteckning": "string"
          }
        },
        "insats": "string",
        "anteckning": "string"
      }
    }
  ],
  "personligKonkurs": [
    {
      "dodsbonummer": "string",
      "insolvensforfarande": {
        "huvud": "string",
        "sekundart": "string",
        "territorielltBegransat": "string"
      },
      "process": {
        "inledd": {
          "malnummer": "string",
          "datum": "2026-07-09",
          "overklaganSenastDatum": "2026-07-09",
          "anmalanFordringarSenastDatum": "2026-07-09",
          "beslutsinstans": {
            "svensk": {
              "kod": "string",
              "klartext": "string"
            },
            "utlandsk": {
              "namn": "string",
              "land": {
                "kod": "string",
                "klartext": "string"
              }
            }
          },
          "overklagande": {
            "beslutsinstans": {
              "svensk": {
                "kod": "string",
                "klartext": "string"
              },
              "utlandsk": {
                "namn": "string",
                "land": {
                  "kod": "string",
                  "klartext": "string"
                }
              }
            }
          }
        },
        "avslutad": {
          "datum": "2026-07-09"
        },
        "upphavd": {
          "malnummer": "string",
          "datum": "2026-07-09",
          "beslutsinstans": {
            "svensk": {
              "kod": "string",
              "klartext": "string"
            },
            "utlandsk": {
              "namn": "string",
              "land": {
                "kod": "string",
                "klartext": "string"
              }
            }
          },
          "overklagande": {
            "datum": "2026-07-09",
            "beslutsinstans": {
              "svensk": {
                "kod": "string",
                "klartext": "string"
              },
              "utlandsk": {
                "namn": "string",
                "land": {
                  "kod": "string",
                  "klartext": "string"
                }
              }
            }
          }
        }
      },
      "konkursforvaltare": {
        "personnamn": {
          "fornamn": "string",
          "efternamn": "string"
        },
        "postadress": {
          "coAdress": "string",
          "adress": "string",
          "postnummer": "string",
          "postort": "string",
          "adressrad1": "string",
          "adressrad2": "string",
          "land": {
            "kod": "string",
            "klartext": "string"
          }
        }
      }
    }
  ],
  "bitradesforbud": {
    "fritext": "string",
    "slutligt": {
      "from": "2026-07-09",
      "tom": "2026-07-09"
    },
    "tillfalligt": {
      "from": "2026-07-09"
    },
    "beslut": {
      "typ": "string",
      "datum": "2026-07-09",
      "beslutsinstans": {
        "kod": "string",
        "klartext": "string"
      }
    }
  },
  "naringsforbud": {
    "fritext": "string",
    "slutligt": {
      "from": "2026-07-09",
      "tom": "2026-07-09"
    },
    "tillfalligt": {
      "from": "2026-07-09"
    },
    "beslut": {
      "typ": "string",
      "datum": "2026-07-09",
      "beslutsinstans": {
        "kod": "string",
        "klartext": "string"
      }
    },
    "undantag": {
      "from": "2026-07-09",
      "tom": "2026-07-09",
      "aterkallatDatum": "2026-07-09"
    },
    "avveckling": "2026-07-09"
  }
}
```

*No links*400

Wrong format on identifier.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*401

Wrong access token.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | Identification of the API-call | string |

*No links*403

Forbidden call, check the scope.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | ID on the call | string |

*No links*404

Personal data or company data is missing.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*default

Unexpected error

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*

This operation retrieves the alternatives on signatory power for a company officer in combination with a company.

#### Parameters

| Name | Description |
| --- | --- |
| X-Request-Id  string  (header) | Client generated ID to call the API. In case of error this will be sent in the error message.  *Example*: d120654c-0d09-481a-8956-940a76474e6b |

#### Request body

Identity of a company officer and of a company. A company officer can be a legal entity or a physical person.

- Example Value
- Schema

```json
{
  "funktionarIdentitetsbeteckning": "string",
  "organisationIdentitetsbeteckning": "string"
}
```

#### Responses

CodeDescriptionLinks200

Reply with requested alternatives on signatory power.

Media type Controls `Accept` header.

- Example Value
- Schema

```json
{
  "firmateckningInformation": [
    {
      "funktionar": {
        "personnamn": {
          "fornamn": "string",
          "efternamn": "string"
        },
        "organisationsnamn": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "namn": "string"
        },
        "identitet": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "identitetsbeteckning": "string"
        },
        "funktionarsroller": [
          {
            "kod": "string",
            "klartext": "string"
          }
        ],
        "utlandskBosattning": {
          "kod": "string",
          "klartext": "string"
        },
        "dispensbosattning": {
          "tillsVidare": true,
          "tomDatum": "2024-12-31"
        },
        "postadress": {
          "coAdress": "string",
          "adress": "string",
          "postnummer": "string",
          "postort": "string",
          "adressrad1": "string",
          "adressrad2": "string",
          "land": {
            "kod": "string",
            "klartext": "string"
          }
        },
        "representerasAv": {
          "personnamn": {
            "fornamn": "string",
            "efternamn": "string"
          },
          "identitet": {
            "typ": {
              "kod": "string",
              "klartext": "string"
            },
            "identitetsbeteckning": "string"
          }
        },
        "insats": "string",
        "anteckning": "string"
      },
      "firmateckningOrganisation": {
        "identitet": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "identitetsbeteckning": "string"
        },
        "namnskyddslopnummer": 1,
        "organisationsnamn": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "namn": "string"
        },
        "organisationsform": {
          "kod": "string",
          "klartext": "string"
        },
        "organisationsstatusar": [
          {
            "kod": "string",
            "klartext": "string",
            "typ": "string",
            "datum": "2026-07-09"
          }
        ],
        "inneliggandeArenden": {
          "antal": 0
        }
      },
      "firmateckningssvar": {
        "utfall": "JA",
        "firmateckningsutfallJaSvar": [
          {
            "alternativ": "TILLSAMMANS",
            "firmateckningsutfallOrsak": {
              "firmateckningskombination": [
                {
                  "typ": {
                    "kod": "string",
                    "klartext": "string"
                  },
                  "ordning": 1,
                  "funktionarsroller": [
                    {
                      "kod": "string",
                      "klartext": "string"
                    }
                  ],
                  "funktionarer": [
                    {
                      "personnamn": {
                        "fornamn": "string",
                        "efternamn": "string"
                      },
                      "organisationsnamn": {
                        "typ": {
                          "kod": "string",
                          "klartext": "string"
                        },
                        "namn": "string"
                      },
                      "identitet": {
                        "typ": {
                          "kod": "string",
                          "klartext": "string"
                        },
                        "identitetsbeteckning": "string"
                      }
                    }
                  ]
                }
              ]
            },
            "namnKanEjListas": false,
            "firmateckningsutfallJatillsammansAlternativ": [
              [
                {
                  "personnamn": {
                    "fornamn": "string",
                    "efternamn": "string"
                  },
                  "organisationsnamn": {
                    "typ": {
                      "kod": "string",
                      "klartext": "string"
                    },
                    "namn": "string"
                  },
                  "identitet": {
                    "typ": {
                      "kod": "string",
                      "klartext": "string"
                    },
                    "identitetsbeteckning": "string"
                  }
                }
              ]
            ]
          }
        ],
        "firmateckningsutfallNejSvar": "EJ_AKTIV_ORGANISATION"
      }
    }
  ]
}
```

*No links*400

Wrong format on identifier.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*401

Wrong access token.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | Identification of the API-call | string |

*No links*403

Forbidden call, check the scope.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | ID on the call | string |

*No links*404

Personal data or company data is missing.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*default

Unexpected error

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*

This operation retrieves either data about a specific case or all cases of a company depending on how the request is designed. In the latter option, it is also possible to specify a time interval to limit the response.

#### Parameters

| Name | Description |
| --- | --- |
| X-Request-Id  string  (header) | Client generated ID to call the API. In case of error this will be sent in the error message.  *Example*: d120654c-0d09-481a-8956-940a76474e6b |

#### Request body

An object to specify `ärendenummer` (case number) or `identitetsbeteckning` (company registration number). In the latter option optionally together with a time interval consisting of from- and/or to dates (`fromdatum` and `tomdatum`).

- Example Value
- Schema

```json
{
  "arendenummer": "1234/2024"
}
```

#### Responses

CodeDescriptionLinks200

Reply with requested case data or all cases (with or without a specific time interval) of a requested company.

Media type Controls `Accept` header.

- Example Value
- Schema

```json
[
  {
    "ankommetDatum": "2024-01-01",
    "skapatTidpunkt": "2008-05-02T13:48:03.580+02:00",
    "avslutatTidpunkt": "2008-10-20T11:13:26.020+02:00",
    "korrigeratDatum": "2024-01-01",
    "arendenummer": "210347/2008",
    "atagandeid": "string",
    "konsumentreferens": "string",
    "inskicksidentitet": "string",
    "uppladdningsid": "string",
    "samladInskicksidentitet": "string",
    "aktid": "UppladdningsidBI=123;UppladdningsidFI=789",
    "arendeslag": {
      "kod": "string",
      "klartext": "string"
    },
    "arendetyp": {
      "kod": "string",
      "klartext": "string"
    },
    "arendeaktorer": [
      {
        "identitet": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "identitetsbeteckning": "string"
        },
        "namn": "string",
        "organisationsform": {
          "kod": "string",
          "klartext": "string"
        },
        "arenderoll": {
          "kod": "string",
          "klartext": "string"
        },
        "kontaktuppgiftIArende": {
          "adressat": "string",
          "postadress": {
            "coAdress": "string",
            "adress": "string",
            "postnummer": "string",
            "postort": "string",
            "adressrad1": "string",
            "adressrad2": "string",
            "land": {
              "kod": "string",
              "klartext": "string"
            }
          },
          "epostadress": "string"
        }
      }
    ],
    "sakfragor": [
      {
        "sakfraga": {
          "kod": "string",
          "klartext": "string"
        },
        "avslutsorsak": {
          "kod": "string",
          "klartext": "string"
        }
      }
    ],
    "arendestatus": {
      "kod": "string",
      "klartext": "string"
    },
    "handlaggningsstatus": {
      "kod": "string",
      "klartext": "string"
    },
    "arendesamband": [
      {
        "utgarFranArendenummer": "string",
        "fortsatterIArendenummer": "string",
        "arendesambandstyp": {
          "kod": "string",
          "klartext": "string"
        }
      }
    ],
    "totalAvgift": 0,
    "betaltBelopp": 0,
    "ocrNummer": "string",
    "arendeinitiativ": {
      "kod": "string",
      "klartext": "string"
    },
    "arendekanal": {
      "kod": "string",
      "klartext": "string"
    },
    "arendekanalUndertyp": {
      "kod": "string",
      "klartext": "string"
    }
  }
]
```

*No links*400

Wrong format on identifier.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*401

Wrong access token.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | Identification of the API-call | string |

*No links*403

Forbidden call, check the scope.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | ID on the call | string |

*No links*404

Personal data or company data is missing.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*default

Unexpected error

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*

This operation retrieves data about historical changes of share capital in a company. It is also possible to specify a time interval to limit the response.

#### Parameters

| Name | Description |
| --- | --- |
| X-Request-Id  string  (header) | Client generated ID to call the API. In case of error this will be sent in the error message.  *Example*: d120654c-0d09-481a-8956-940a76474e6b |

#### Request body

An object to specify `identitetsbeteckning` (company registration number). Optionally together with a time interval consisting of from- and/or to dates (`fromdatum` and `tomdatum`).

- Example Value
- Schema

```json
{
  "identitetsbeteckning": "5560123456",
  "fromdatum": "2024-01-01",
  "tomdatum": "2024-12-31"
}
```

#### Responses

CodeDescriptionLinks200

Reply with requested changes of share capital (with or without a specific time interval) of a requested company.

Media type Controls `Accept` header.

- Example Value
- Schema

```json
{
  "identitet": {
    "typ": {
      "kod": "string",
      "klartext": "string"
    },
    "identitetsbeteckning": "string"
  },
  "organisationsnamn": {
    "typ": {
      "kod": "string",
      "klartext": "string"
    },
    "namn": "string"
  },
  "organisationsform": {
    "kod": "string",
    "klartext": "string"
  },
  "organisationsstatusar": [
    {
      "kod": "string",
      "klartext": "string",
      "typ": "string",
      "datum": "2026-07-09"
    }
  ],
  "gallandeAktieinformation": {
    "aktiekapital": {
      "belopp": 12000,
      "valuta": "SEK"
    },
    "antalAktier": 1200,
    "aktiegranser": {
      "aktiekapitalGranser": {
        "lagst": 25000,
        "hogst": 100000
      },
      "antalAktierGranser": {
        "lagst": 1000,
        "hogst": 10000
      },
      "valuta": "SEK"
    },
    "aktieslag": [
      {
        "namn": "A",
        "antal": 1000,
        "aktieslagGranser": {
          "lagst": 1000,
          "hogst": 10000
        },
        "rostvarde": "1"
      }
    ],
    "fritext": "Antalet aktier av respektive slag får motsvara högst hela antalet aktier i bolaget.",
    "kvotvarde": {
      "belopp": 12000,
      "valuta": "SEK"
    },
    "nedsattningPagar": true
  },
  "aktiekapitalforandringar": [
    {
      "arende": {
        "arendenummer": "1234/2024",
        "avslutatTidpunkt": "2000-01-01T00:00:00.000+02:00"
      },
      "aktieinformation": {
        "aktiekapital": {
          "belopp": 12000,
          "valuta": "SEK"
        },
        "antalAktier": 1200,
        "aktiegranser": {
          "aktiekapitalGranser": {
            "lagst": 25000,
            "hogst": 100000
          },
          "antalAktierGranser": {
            "lagst": 1000,
            "hogst": 10000
          },
          "valuta": "SEK"
        },
        "aktieslag": [
          {
            "namn": "A",
            "antal": 1000,
            "aktieslagGranser": {
              "lagst": 1000,
              "hogst": 10000
            },
            "rostvarde": "1"
          }
        ],
        "fritext": "Antalet aktier av respektive slag får motsvara högst hela antalet aktier i bolaget.",
        "kvotvarde": {
          "belopp": 12000,
          "valuta": "SEK"
        },
        "nedsattningPagar": true
      },
      "aktiekapitalforandring": [
        {
          "lopnummer": "string",
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "valuta": {
            "kod": "string",
            "klartext": "string"
          },
          "aktiekapital": {
            "belopp": 0,
            "lagst": 25000,
            "hogst": 100000,
            "betaltInklusiveOverkurs": 100000
          },
          "antalAktier": 0,
          "beslutAvInstans": {
            "instanstyp": {
              "kod": "string",
              "klartext": "string"
            },
            "beslutsdatum": "2026-07-09"
          },
          "nyemission": {
            "betalningssatt": [
              {
                "kod": "string",
                "klartext": "string"
              }
            ],
            "belopp": 0,
            "betaltAntalAktier": 0,
            "fullbetalning": true,
            "delregistrering": true
          },
          "minskning": {
            "minskningAvAktiekapitalPagar": true,
            "forfallen": {
              "beslutAvInstans": {
                "instanstyp": {
                  "kod": "string",
                  "klartext": "string"
                },
                "beslutsdatum": "2026-07-09"
              }
            },
            "tillstand": {
              "beviljatAvInstans": {
                "instanstyp": {
                  "kod": "string",
                  "klartext": "string"
                },
                "beslutsdatum": "2026-07-09"
              }
            },
            "belopp": 0
          },
          "genom": [
            {
              "kod": "string",
              "klartext": "string"
            }
          ],
          "andamal": [
            {
              "kod": "string",
              "klartext": "string"
            }
          ],
          "aktieslag": [
            {
              "namn": "A",
              "antal": 1000,
              "rostvarde": "1"
            }
          ],
          "fritext": "string",
          "skuldebrevUtgivetIArendenummer": "string",
          "aktiekapitalEfterAndring": 0
        }
      ]
    }
  ],
  "bemyndiganden": [
    {
      "arende": {
        "arendenummer": "1234/2024",
        "avslutatTidpunkt": "2000-01-01T00:00:00.000+02:00"
      },
      "bemyndigandegrupper": [
        {
          "lopnummer": "string",
          "fritext": "string",
          "bemyndiganden": [
            {
              "typ": {
                "kod": "string",
                "klartext": "string"
              },
              "bemyndigandeDatum": "2026-07-09",
              "bemyndigandeAnvandsFore": {
                "ordinarieBolagsstammaAr": 0,
                "annatDatum": "2026-07-09"
              }
            }
          ]
        }
      ]
    }
  ],
  "skuldebrev": [
    {
      "arende": {
        "arendenummer": "1234/2024",
        "avslutatTidpunkt": "2000-01-01T00:00:00.000+02:00"
      },
      "skuldebrev": {
        "lopnummer": "string",
        "typ": {
          "kod": "string",
          "klartext": "string"
        },
        "beslutAvInstans": {
          "instanstyp": {
            "kod": "string",
            "klartext": "string"
          },
          "beslutsdatum": "2026-07-09"
        },
        "valuta": {
          "kod": "string",
          "klartext": "string"
        },
        "forandringsbelopp": {
          "beslutatBelopp": 0,
          "lagst": 25000,
          "hogst": 100000
        },
        "tecknatBelopp": 0,
        "aktieslag": "string",
        "aktiekapitalKanOkasMedBelopp": 0,
        "teckningsoptioner": {
          "belopp": 0,
          "aktieteckning": {
            "from": "2026-07-09",
            "tom": "2026-07-09"
          },
          "antal": {
            "faktisktAntal": 0,
            "lagst": 0,
            "hogst": 0
          },
          "utanLan": true,
          "medLan": true,
          "tidForNyteckning": {
            "from": "2026-07-09",
            "tom": "2026-07-09"
          }
        },
        "konvertibler": {
          "belopp": 0,
          "utbyte": {
            "from": "2026-07-09",
            "tom": "2026-07-09"
          }
        },
        "fritext": "string"
      }
    }
  ]
}
```

*No links*400

Wrong format on identifier.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*401

Wrong access token.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | Identification of the API-call | string |

*No links*403

Forbidden call, check the scope.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | ID on the call | string |

*No links*404

Personal data or company data is missing.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*default

Unexpected error

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*

This operation retrieves data about an individual’s or a company’s assignments in other companies.

#### Parameters

| Name | Description |
| --- | --- |
| X-Request-Id  string  (header) | Client generated ID to call the API. In case of error this will be sent in the error message.  *Example*: d120654c-0d09-481a-8956-940a76474e6b |

#### Request body

An object to specify `identitetsbeteckning` (company registration number or personal identity number). Optionally together with pagination, filter and sort parameters.

- Example Value
- Schema

```json
{
  "identitetsbeteckning": "string",
  "paginering": {
    "sida": 0,
    "antalPerSida": 10
  },
  "sortering": {
    "attribut": "ORGANISATIONSFORM",
    "sorteringsordning": "ASC"
  },
  "filtrering": {
    "must": [
      {}
    ],
    "mustNot": [
      {}
    ],
    "should": [
      {}
    ]
  }
}
```

#### Responses

CodeDescriptionLinks200

Reply with the individual’s or a company’s assignments in other companies.

Media type Controls `Accept` header.

- Example Value
- Schema

```json
{
  "totaltAntalTraffar": 79,
  "sida": 0,
  "antalPerSida": 10,
  "funktionarsOrganisationsengagemang": [
    {
      "organisation": {
        "identitet": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "identitetsbeteckning": "string"
        },
        "namnskyddslopnummer": 2,
        "organisationsnamn": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "namn": "string"
        },
        "organisationsform": {
          "kod": "string",
          "klartext": "string"
        },
        "organisationsstatusar": [
          {
            "kod": "string",
            "klartext": "string",
            "typ": "string",
            "datum": "2026-07-09"
          }
        ]
      },
      "funktionar": {
        "personnamn": {
          "fornamn": "string",
          "efternamn": "string"
        },
        "organisationsnamn": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "namn": "string"
        },
        "identitet": {
          "typ": {
            "kod": "string",
            "klartext": "string"
          },
          "identitetsbeteckning": "string"
        },
        "funktionarsroller": [
          {
            "kod": "string",
            "klartext": "string"
          }
        ],
        "arFirmatecknare": "JA",
        "anteckning": "string"
      }
    }
  ]
}
```

*No links*400

Wrong format on identifier.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*401

Wrong access token.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | Identification of the API-call | string |

*No links*403

Forbidden call, check the scope.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | ID on the call | string |

*No links*404

Personal data or company data is missing.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*default

Unexpected error

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*

This operation retrieves data about an company’s financial reports.

#### Parameters

| Name | Description |
| --- | --- |
| X-Request-Id  string  (header) | Client generated ID to call the API. In case of error this will be sent in the error message.  *Example*: d120654c-0d09-481a-8956-940a76474e6b |

#### Request body

An object to specify `identitetsbeteckning` (company registration number or personal identity number).

- Example Value
- Schema

```json
{
  "identitetsbeteckning": "string",
  "fromdatum": "2024-01-01",
  "tomdatum": "2024-12-31"
}
```

#### Responses

CodeDescriptionLinks200

Reply with the company’s financial reports.

Media type Controls `Accept` header.

- Example Value
- Schema

```json
{
  "identitetsbeteckning": "string",
  "finansiellaRapporter": [
    {
      "arende": {
        "arendenummer": "123456/2025",
        "avslutatTidpunkt": "2024-12-31T12:12+02:00"
      },
      "rakenskapsperioder": [
        {
          "start": "2024-12-31",
          "slut": "2024-12-31",
          "arsredovisningar": [
            {
              "rapporteringsperiod": {
                "periodFrom": "2024-12-31",
                "periodTom": "2024-12-31"
              },
              "rapporttyp": {
                "kod": "string",
                "klartext": "string"
              },
              "ankomsttidpunkt": "string",
              "registreradTidpunkt": "string",
              "arsredovisningsinnehall": [
                {
                  "kod": "string",
                  "klartext": "string"
                }
              ],
              "brister": [
                {
                  "kod": "string",
                  "klartext": "string"
                }
              ],
              "handlaggningAvslutadDatum": "string"
            }
          ],
          "arsredovisningspaminnelse": {
            "skickadTidpunkt": "string",
            "arsredovisningspaminnelsetyp": {
              "kod": "string",
              "klartext": "string"
            }
          },
          "vinstutdelning": {
            "beslutadDatum": "string",
            "valuta": {
              "kod": "string",
              "klartext": "string"
            },
            "belopp": 0,
            "vinstutdelningstyp": {
              "kod": "string",
              "klartext": "string"
            }
          },
          "fortsattStamma": {
            "stammodatum": "string",
            "fritext": "string"
          }
        }
      ]
    }
  ]
}
```

*No links*400

Wrong format on identifier.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*401

Wrong access token.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | Identification of the API-call | string |

*No links*403

Forbidden call, check the scope.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | ID on the call | string |

*No links*404

Personal data or company data is missing.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*default

Unexpected error

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*

With this operation you can retrieve data about business mortgages.

#### Parameters

| Name | Description |
| --- | --- |
| X-Request-Id  string  (header) | Client generated ID to call the API. In case of error this will be sent in the attribute `requestId` or as a header attribute.  *Example*: d120654c-0d09-481a-8956-940a76474e6b |

#### Request body

An object that allows you to specify one of the following parameters `identitetsbeteckning` (company registration number), `inteckningsnummer` (business mortgage number) or `inteckningsid` (business mortgage identity) to retrieve information about business mortgages.

- Example Value
- Schema

```json
{
  "identitetsbeteckning": "5561234567",
  "inteckningsnummer": "19911208.34.70",
  "inteckningsid": "2003123114474437"
}
```

#### Responses

CodeDescriptionLinks200

Reply with business mortgages for the specified search criteria.

Media type Controls `Accept` header.

- Example Value
- Schema

```json
{
  "foretagsinteckningar": [
    {
      "idNaringsidkarkombination": "1233123114474437",
      "naringsidkare": [
        {
          "identitet": {
            "typ": {
              "kod": "string",
              "klartext": "string"
            },
            "identitetsbeteckning": "5567223705"
          },
          "organisationsnamn": "Testbolaget Aktiebolag",
          "personnamn": {
            "fornamn": "string",
            "efternamn": "string"
          }
        }
      ],
      "anmarkningarNaringsidkare": [
        {
          "dagboksnummer": "19880120.0.04",
          "fritext": "Anteckning"
        }
      ],
      "upplagg": [
        {
          "verksamhetsbegransning": "INDUSTRIELL RÖRELSE VID KRAFTSTATION FÖR FRAMSTÄLLNING AV ELEKTRISK ENERGI",
          "geografiskBegransning": "SKARABORGS LÄN",
          "upplaggsanteckningar": {
            "anteckningarPaUpplagget": [
              {
                "dagboksnummer": "19570120.0.04",
                "fritext": "Anteckning på upplägget",
                "anmarkningar": [
                  {
                    "dagboksnummer": "19880120.0.04",
                    "fritext": "Anteckning"
                  }
                ]
              }
            ],
            "anmarkningarPaUpplaggetsVerksamhet": [
              {
                "dagboksnummer": "19880120.0.04",
                "fritext": "Anteckning"
              }
            ]
          },
          "inteckningar": [
            {
              "inteckningsanmarkningar": [
                {
                  "dagboksnummer": "19880321.1.01",
                  "ursprungligtBeslutDagboksnummer": "19860321.1.03",
                  "fritext": "Anteckning"
                }
              ],
              "inteckningsid": "1234567890123456",
              "inteckningsnummer": "19680422.1.74",
              "skriftligtInteckningsbrev": true,
              "likaRattSomOrdningsnummer": 2,
              "beloppInteckning": {
                "valuta": {
                  "kod": "string",
                  "klartext": "string"
                },
                "belopp": 50000
              },
              "beviljad": true,
              "ordningsnummer": 1,
              "innehavare": [
                {
                  "dagboksnummer": "19700123.1.74",
                  "namn": "PKBANKEN",
                  "postadress": {
                    "coAdress": "c/o AB Testbolaget",
                    "adress": "BOX 123",
                    "postnummer": "11111",
                    "postort": "TESTHOLMEN",
                    "land": {
                      "kod": "string",
                      "klartext": "string"
                    }
                  }
                }
              ],
              "sparrPgaForkommenHandling": false
            }
          ],
          "beloppFusion": {
            "valuta": {
              "kod": "string",
              "klartext": "string"
            },
            "belopp": 50000
          },
          "inteckningarTotalt": {
            "beviljade": {
              "antal": 2,
              "summaBeviljade": [
                {
                  "valuta": {
                    "kod": "string",
                    "klartext": "string"
                  },
                  "belopp": 50000
                }
              ]
            },
            "ejBeviljade": {
              "antal": 1,
              "summaEjBeviljade": [
                {
                  "valuta": {
                    "kod": "string",
                    "klartext": "string"
                  },
                  "belopp": 50000
                }
              ]
            }
          }
        }
      ]
    }
  ]
}
```

*No links*400

Wrong format on identifier.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*401

Wrong access token.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | Identification of the API-call | string |

*No links*403

Forbidden call, check the scope.

#### Headers:

| Name | Description | Type |
| --- | --- | --- |
| X-Request-Id | ID on the call | string |

*No links*404

Personal data or company data is missing.

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*default

Unexpected error

Media type

- Example Value
- Schema

```json
{
  "type": "urn:bolagsverket:error:validation",
  "instance": "validation.client",
  "status": 400,
  "timestamp": "2021-02-03T13:45:16.953149+02:00",
  "requestId": "d120654c-0d09-481a-8956-940a76474e6b",
  "title": "Fel format",
  "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",
  "code": "FM003",
  "source": "identitetsbeteckning.identitet.id"
}
```

*No links*

### pingAPI to control the status of the service

With this operation you can check to see that the API is up and running.

#### Parameters

No parameters

#### Responses

| Code | Description | Links |
| --- | --- | --- |
| 200 | OK | *No links* |
| 503 | Server Unavailable | *No links* |
| default | Unexpected error  Media type Controls `Accept` header.  - Example Value - Schema  ```json {   "type": "urn:bolagsverket:error:validation",   "instance": "validation.client",   "status": 400,   "timestamp": "2021-02-03T13:45:16.953149+02:00",   "requestId": "d120654c-0d09-481a-8956-940a76474e6b",   "title": "Fel format",   "detail": "Identitetsbeteckning måste vara 10 eller 12 siffror: A7696151111",   "code": "FM003",   "source": "identitetsbeteckning.identitet.id" } ``` | *No links* |