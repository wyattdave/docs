---
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
  metadata:
    visible: false
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
---

# JSON Export Schema (oData)

```json
{
    "$schema": "http://json-schema.org/draft-07/schema#",
    "title": "Generated schema for Captcha Demos",
    "type": "object",
    "properties": {
        "AppConfig": {
            "type": "object",
            "properties": {
                "Name": {
                    "type": "string"
                },
                "ScreenCount": {
                    "type": "integer"
                },
                "ComponentCount": {
                    "type": "integer"
                },
                "VarCount": {
                    "type": "integer"
                },
                "ConnectionCount": {
                    "type": "integer"
                },
                "AppId": {
                    "type": "string"
                },
                "AppType": {
                    "type": "string"
                },
                "AppDescript": {
                    "type": "string"
                },
                "AppAPILimit": {
                    "type": "integer"
                },
                "Version": {
                    "type": "string"
                },
                "PCF": {
                    "type": "boolean"
                },
                "AppError": {
                    "type": "integer"
                },
                "AppKey": {
                    "type": "string"
                }
            }
        },
        "Solution": {
            "type": "object",
            "properties": {
                "Name": {
                    "type": "string"
                },
                "UniqueName": {
                    "type": "string"
                },
                "Version": {
                    "type": "string"
                },
                "Managed": {
                    "type": "integer"
                },
                "Publisher": {
                    "type": "string"
                }
            }
        },
        "Code": {
            "type": "string"
        },
        "Screens": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Screen": {
                        "type": "string"
                    },
                    "CentCount": {
                        "type": "integer"
                    },
                    "Rules": {
                        "type": "array",
                        "items": {
                            "type": "object",
                            "properties": {
                                "Property": {
                                    "type": "string"
                                },
                                "Category": {
                                    "type": "string"
                                },
                                "InvariantScript": {
                                    "type": "string"
                                },
                                "RuleProviderType": {
                                    "type": "string"
                                }
                            }
                        }
                    }
                }
            }
        },
        "ComponentTotals": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Component": {
                        "type": "string"
                    },
                    "Count": {
                        "type": "integer"
                    }
                }
            }
        },
        "Components": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Screen": {
                        "type": "string"
                    },
                    "Name": {
                        "type": "string"
                    },
                    "Type": {
                        "type": "string"
                    },
                    "Property": {
                        "type": "string"
                    },
                    "Script": {
                        "type": "string"
                    }
                }
            }
        },
        "ComponentsYAML": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Component": {
                        "type": "string"
                    },
                    "YAML": {
                        "type": "string"
                    }
                }
            }
        },
        "Variables": {
            "type": "object",
            "properties": {
                "Local": {
                    "type": "array",
                    "items": {
                        "type": "object",
                        "properties": {
                            "Variable": {
                                "type": "string"
                            },
                            "Screen": {
                                "type": "string"
                            },
                            "Set": {
                                "type": "integer"
                            },
                            "Used": {
                                "type": "integer"
                            }
                        }
                    }
                },
                "Global": {
                    "type": "array",
                    "items": {
                        "type": "object",
                        "properties": {
                            "Variable": {
                                "type": "string"
                            },
                            "Type": {
                                "type": "string"
                            },
                            "Set": {
                                "type": "integer"
                            },
                            "Used": {
                                "type": "integer"
                            }
                        }
                    }
                },
                "Formulas": {
                    "type": "string"
                },
                "Collections": {
                    "type": "array",
                    "items": {
                        "type": "object",
                        "properties": {
                            "Variable": {
                                "type": "string"
                            },
                            "Set": {
                                "type": "integer"
                            },
                            "Used": {
                                "type": "integer"
                            }
                        }
                    }
                }
            }
        },
        "Connections": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Name": {
                        "type": "string"
                    },
                    "ApiId": {
                        "type": "string"
                    }
                }
            }
        },
        "DataSources": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Name": {
                        "type": "string"
                    },
                    "DatasetName": {
                        "type": "string"
                    },
                    "EnvironmentVar": {
                        "type": "string"
                    }
                }
            }
        },
        "Flows": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Name": {
                        "type": "string"
                    },
                    "Flow": {
                        "type": "string"
                    }
                }
            }
        },
        "Tests": {
            "type": "object",
            "properties": {
                "Suites": {
                    "type": "array",
                    "items": {
                        "type": "object",
                        "properties": {
                            "SuiteTrigger": {
                                "type": "string"
                            },
                            "Action": {
                                "type": "string"
                            }
                        }
                    }
                },
                "Tests": {
                    "type": "array",
                    "items": {
                        "type": "object",
                        "properties": {
                            "Suite": {
                                "type": "string"
                            },
                            "Test": {
                                "type": "string"
                            },
                            "TestDescription": {
                                "type": "string"
                            },
                            "Action": {
                                "type": "string"
                            }
                        }
                    }
                }
            }
        },
        "MissingDependencies": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Name": {
                        "type": "string"
                    },
                    "Type": {
                        "type": "integer"
                    },
                    "NameReq": {
                        "type": "string"
                    },
                    "ParentId": {
                        "type": "string"
                    }
                }
            }
        },
        "EnvironmentVariables": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Name": {
                        "type": "string"
                    },
                    "Description": {
                        "type": "string"
                    },
                    "API": {
                        "type": "string"
                    },
                    "DataType": {
                        "type": "string"
                    },
                    "Type": {
                        "type": "integer"
                    }
                }
            }
        },
        "ConnectionReferences": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Name": {
                        "type": "string"
                    },
                    "Id": {
                        "type": "string"
                    },
                    "Type": {
                        "type": "string"
                    }
                }
            }
        },
        "SolutionFlows": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Name": {
                        "type": "string"
                    },
                    "Id": {
                        "type": "string"
                    },
                    "SubProcess": {
                        "type": "integer"
                    }
                }
            }
        },
        "Tables": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "Name": {
                        "type": "string"
                    },
                    "Id": {
                        "type": "string"
                    },
                    "Description": {
                        "type": "string"
                    }
                }
            }
        }
    }
```
