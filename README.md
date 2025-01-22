  },
  "paths": {
    "/api/Batch/Job/{jobNumber}/Status": {
      "get": {
        "tags": [
          "Batch"
        ],
        "operationId": "886826ef-9e51-412f-941a-ab8eb0ffe1b6",
        "parameters": [
          {
            "name": "jobNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Batch/Job/{jobNumber}/Result/{page}": {
      "get": {
        "tags": [
          "Batch"
        ],
        "operationId": "41a26993-f925-483a-815b-dbc50743f9e5",
        "parameters": [
          {
            "name": "jobNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "page",
            "in": "path",
            "required": true,
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Batch/Search": {
      "put": {
        "tags": [
          "Batch"
        ],
        "operationId": "3e3f2ba7-723d-40a8-9a28-6f4ddccd9baa",
        "parameters": [
          {
            "name": "Type",
            "in": "query",
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "StartDate.FromDate",
            "in": "query",
            "schema": {
              "type": "string",
              "format": "date-time"
            }
          },
          {
            "name": "StartDate.ToDate",
            "in": "query",
            "schema": {
              "type": "string",
              "format": "date-time"
            }
          },
          {
            "name": "StartDate.HasValue",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "EndDate.FromDate",
            "in": "query",
            "schema": {
              "type": "string",
              "format": "date-time"
            }
          },
          {
            "name": "EndDate.ToDate",
            "in": "query",
            "schema": {
              "type": "string",
              "format": "date-time"
            }
          },
          {
            "name": "EndDate.HasValue",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Status",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Process.RemoteJobStatus"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/CatalogSource": {
      "get": {
        "tags": [
          "CatalogSource"
        ],
        "operationId": "2b212ffc-d45f-4196-8cad-cf567a0fdd99",
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/CatalogSource/{id}": {
      "get": {
        "tags": [
          "CatalogSource"
        ],
        "operationId": "9a2ee048-d58e-43bf-a696-5f44058cdd49",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "delete": {
        "tags": [
          "CatalogSource"
        ],
        "operationId": "e4c791a1-187d-4219-aa5e-81e907efa20f",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/CatalogSource/Channel/{channelId}/{name}": {
      "get": {
        "tags": [
          "CatalogSource"
        ],
        "operationId": "20c79cdf-a5ae-4d23-81db-0d8e341c3110",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "name",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "delete": {
        "tags": [
          "CatalogSource"
        ],
        "operationId": "18f15114-2ab1-45d0-a4e3-4df3c302d4ef",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "name",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/CatalogSource/{sourceId}/Columns": {
      "post": {
        "tags": [
          "CatalogSourceColumn"
        ],
        "operationId": "ef317367-d60c-45de-9180-362307f8efec",
        "parameters": [
          {
            "name": "sourceId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/CatalogSource.Column"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/CatalogSource.Column"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/CatalogSource.Column"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK",
            "content": {
              "text/plain": {
                "schema": {
                  "type": "string",
                  "format": "uuid"
                }
              },
              "application/json": {
                "schema": {
                  "type": "string",
                  "format": "uuid"
                }
              },
              "text/json": {
                "schema": {
                  "type": "string",
                  "format": "uuid"
                }
              }
            }
          }
        }
      }
    },
    "/api/CatalogSource/{sourceId}/Columns/{id}": {
      "delete": {
        "tags": [
          "CatalogSourceColumn"
        ],
        "operationId": "e7838ca4-1af1-4332-a0a3-79a424314d1e",
        "parameters": [
          {
            "name": "sourceId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "default": {
            "description": "Error",
            "content": {
              "text/plain": {
                "schema": {
                  "$ref": "#/components/schemas/Microsoft.AspNetCore.Mvc.ProblemDetails"
                }
              },
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/Microsoft.AspNetCore.Mvc.ProblemDetails"
                }
              },
              "text/json": {
                "schema": {
                  "$ref": "#/components/schemas/Microsoft.AspNetCore.Mvc.ProblemDetails"
                }
              }
            }
          }
        }
      }
    },
    "/api/CatalogSource/{sourceId}/Columns/{columnId}/ColumnMaps": {
      "post": {
        "tags": [
          "ColumnMaps"
        ],
        "operationId": "0008b43f-0b2e-4af6-80ab-8cb1f32358f6",
        "parameters": [
          {
            "name": "sourceId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "columnId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "AttributeCode",
            "in": "query",
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "MapType",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/CatalogSource.MapTypeType"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/CatalogSource/{sourceId}/ColumnMaps/{id}": {
      "delete": {
        "tags": [
          "ColumnMaps"
        ],
        "operationId": "a205dd59-1b49-4c98-9b0a-34d7f7acc9b0",
        "parameters": [
          {
            "name": "sourceId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Inventory/Adjustment": {
      "put": {
        "tags": [
          "Inventory"
        ],
        "operationId": "64489854-7bbb-49f7-9f85-0736e3bb416f",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.Adjustment.Adjustment"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.Adjustment.Adjustment"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.Adjustment.Adjustment"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Inventory/Transfer": {
      "put": {
        "tags": [
          "Inventory"
        ],
        "operationId": "898b7aec-df0d-4cb5-b56b-388fcc594be4",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.Transfer.Transfer"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.Transfer.Transfer"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.Transfer.Transfer"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Inventory/Assemble": {
      "put": {
        "tags": [
          "Inventory"
        ],
        "operationId": "94a12c08-825c-4e91-bfcb-e02d3f92f4fe",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.Assembly.Assembly"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.Assembly.Assembly"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.Assembly.Assembly"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Inventory/PutAway/Search": {
      "put": {
        "tags": [
          "Inventory"
        ],
        "operationId": "d8db6c9b-4bbd-4720-9b09-8d378e451882",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.PutAway.PutAwayRequest"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.PutAway.PutAwayRequest"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.PutAway.PutAwayRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Inventory/{channelSku}/{locationCode}": {
      "put": {
        "tags": [
          "Inventory"
        ],
        "operationId": "5f534cb4-e1a5-4c92-805c-f50b6cf36d7e",
        "parameters": [
          {
            "name": "channelSku",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "locationCode",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.AvailableQuantity"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.AvailableQuantity"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.AvailableQuantity"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/InventoryEvent": {
      "get": {
        "tags": [
          "InventoryEvent"
        ],
        "operationId": "8903d9ec-e4b2-4b6c-9875-9c4159316369",
        "parameters": [
          {
            "name": "NewOnly",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "FromDate",
            "in": "query",
            "schema": {
              "type": "string",
              "format": "date-time"
            }
          },
          {
            "name": "ToDate",
            "in": "query",
            "schema": {
              "type": "string",
              "format": "date-time"
            }
          },
          {
            "name": "LocationCode",
            "in": "query",
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "OrderId",
            "in": "query",
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "Type",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Inventory.InventoryEventType"
            }
          },
          {
            "name": "Page",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          },
          {
            "name": "PageSize",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          },
          {
            "name": "Skip",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/InventoryEvent/{id}": {
      "get": {
        "tags": [
          "InventoryEvent"
        ],
        "operationId": "5bb3407d-aa94-4acf-9352-4f8912bdaf46",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "integer",
              "format": "int64"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Transfer": {
      "get": {
        "tags": [
          "InventoryEvent"
        ],
        "operationId": "216b3adc-f9d3-4a62-a2c4-9c996dd595f6",
        "parameters": [
          {
            "name": "NewOnly",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "FromDate",
            "in": "query",
            "schema": {
              "type": "string",
              "format": "date-time"
            }
          },
          {
            "name": "ToDate",
            "in": "query",
            "schema": {
              "type": "string",
              "format": "date-time"
            }
          },
          {
            "name": "LocationCode",
            "in": "query",
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "OrderId",
            "in": "query",
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "Type",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Inventory.InventoryEventType"
            }
          },
          {
            "name": "Page",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          },
          {
            "name": "PageSize",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          },
          {
            "name": "Skip",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Transfer/{id}": {
      "get": {
        "tags": [
          "InventoryEvent"
        ],
        "operationId": "98996943-4493-4b04-a262-9fe1e57dad1c",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "integer",
              "format": "int64"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/InventoryEvent/Search": {
      "put": {
        "tags": [
          "InventoryEvent"
        ],
        "operationId": "8f7ffd5d-f6e7-43a4-a85d-9c1cef739b98",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.EventSearch"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.EventSearch"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Inventory.EventSearch"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/InventoryEvent/Search/Next/{id}": {
      "get": {
        "tags": [
          "InventoryEvent"
        ],
        "operationId": "5457bda5-b6d2-4ca2-a616-9dfabad00ccd",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "put": {
        "tags": [
          "InventoryEvent"
        ],
        "operationId": "5457bda5-b6d2-4ca2-a616-9dfabad00ccd",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/{id}": {
      "get": {
        "tags": [
          "PurchaseOrder"
        ],
        "operationId": "6f6117b9-1283-4351-a70d-fd605c0bd01a",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "delete": {
        "tags": [
          "PurchaseOrder"
        ],
        "operationId": "291b15ac-ed96-4603-8b9b-9cb2feee0ab5",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "SalesOrderReview",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/Channel/{channelId}/{orderNumber}": {
      "get": {
        "tags": [
          "PurchaseOrder"
        ],
        "operationId": "d5cb10b3-a408-4609-b26b-efed6fd18221",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "delete": {
        "tags": [
          "PurchaseOrder"
        ],
        "operationId": "cff2aeac-e409-4633-b051-03eadd1a17ef",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "SalesOrderReview",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder": {
      "post": {
        "tags": [
          "PurchaseOrder"
        ],
        "operationId": "94002d33-44a6-417e-80b8-302caf9a4e41",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseOrder"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseOrder"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseOrder"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/{id}/Receive": {
      "put": {
        "tags": [
          "PurchaseOrder"
        ],
        "operationId": "60901967-64ad-426a-a408-4e7c2bfc2467",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseReceipt"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseReceipt"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseReceipt"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/Channel/{channelId}/{orderNumber}/Receive": {
      "put": {
        "tags": [
          "PurchaseOrder"
        ],
        "operationId": "320c76bc-ae67-4d60-b1b1-a0751a3d43ae",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseReceipt"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseReceipt"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseReceipt"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/Search": {
      "put": {
        "tags": [
          "PurchaseOrder"
        ],
        "operationId": "13c8b4f9-2bdf-48c6-a4d2-aae930132cfe",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseOrderSearch"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseOrderSearch"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Supplier.PurchaseOrderSearch"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/Search/Next/{id}": {
      "get": {
        "tags": [
          "PurchaseOrder"
        ],
        "operationId": "270e9d8c-cc08-442b-a30b-20ba0df3f7eb",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "put": {
        "tags": [
          "PurchaseOrder"
        ],
        "operationId": "270e9d8c-cc08-442b-a30b-20ba0df3f7eb",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/{id}/Shipment": {
      "put": {
        "tags": [
          "PurchaseOrderShipment"
        ],
        "operationId": "3d7a6f83-8b7a-4418-bdaf-92b62f90ac1d",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/Channel/{channelId}/{orderNumber}/Shipment": {
      "put": {
        "tags": [
          "PurchaseOrderShipment"
        ],
        "operationId": "dc80c07d-c3b4-4a66-b823-19ee54ca70be",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/{id}/Complete": {
      "put": {
        "tags": [
          "PurchaseOrderShipment"
        ],
        "operationId": "1a990792-dd70-48cc-a103-c81ed300750e",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/Channel/{channelId}/{orderNumber}/Complete": {
      "put": {
        "tags": [
          "PurchaseOrderShipment"
        ],
        "operationId": "0f6d80e5-6a67-41d0-8c58-811fa4561aeb",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}": {
      "get": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "c4fda8de-b4c6-4135-905e-28f48f3dbacd",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "OriginalStructure",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Acknowledge",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "ResponseType",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Sales.ResponseTypeType"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK",
            "content": {
              "text/plain": {
                "schema": {
                  "$ref": "#/components/schemas/Sales.SalesOrder"
                }
              },
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/Sales.SalesOrder"
                }
              },
              "text/json": {
                "schema": {
                  "$ref": "#/components/schemas/Sales.SalesOrder"
                }
              }
            }
          }
        }
      },
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "225a949b-b63c-4dcd-bd5f-5e7e764e30c7",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "OriginalStructure",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Acknowledge",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "ResponseType",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Sales.ResponseTypeType"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrder"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrder"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrder"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}": {
      "get": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "36d3fb70-e13b-4fb5-8d44-b70523bd21f9",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "OriginalStructure",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Acknowledge",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "ResponseType",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Sales.ResponseTypeType"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "6a9478f7-4687-47c4-8daf-a6dd73340435",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "OriginalStructure",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Acknowledge",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "ResponseType",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Sales.ResponseTypeType"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrder"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrder"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrder"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "delete": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "65c2fd0c-3215-44b2-b256-968c2445dbd9",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}/Acknowledge": {
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "9ed63c9b-9337-41de-a5df-b273ee06ab6f",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "OriginalStructure",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Acknowledge",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "ResponseType",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Sales.ResponseTypeType"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/Acknowledge": {
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "c36f04c7-f0ae-4fe4-9e86-7594fcb6b7d8",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "OriginalStructure",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Acknowledge",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "ResponseType",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Sales.ResponseTypeType"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}/History": {
      "get": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "03d4ad74-2bd0-4f18-b914-5f8e64233d00",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/History": {
      "get": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "bfd5bef9-6027-405c-b691-597079f01481",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder": {
      "post": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "e226a356-4386-45ef-8b56-0aa9d877155f",
        "parameters": [
          {
            "name": "Hold",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "AssignFulfillment",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrder"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrder"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrder"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{id}": {
      "delete": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "7fceb79f-b363-4f27-bba9-7257a38a5d24",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/Picked": {
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "c102d692-165e-412a-a307-dc4c336ffba0",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{id}/Picked": {
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "0fdbcbf1-6221-4ab2-94e9-b393efb613cf",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/Clone/{newNumber}": {
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "355a00c5-b163-49ce-a6ee-968dc03b7645",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "newNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "Hold",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "AssignFulfillment",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}/Clone/{newNumber}": {
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "da4eecf8-d707-4fb0-87e6-03c29274552d",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "newNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "Hold",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "AssignFulfillment",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}/Fulfillment": {
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "0f1f0661-a173-4a66-8ddf-886385d58973",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "OriginalStructure",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Acknowledge",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "ResponseType",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Sales.ResponseTypeType"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.FulfillmentAssignment"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.FulfillmentAssignment"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.FulfillmentAssignment"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/Fulfillment": {
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "933ab310-8ff2-4609-8fc9-fd108192af2d",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "OriginalStructure",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Acknowledge",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "ResponseType",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Sales.ResponseTypeType"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.FulfillmentAssignment"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.FulfillmentAssignment"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.FulfillmentAssignment"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Search": {
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "99687dd2-03f5-4933-8ce1-b99008eca14c",
        "parameters": [
          {
            "name": "SingleAllocation",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "OriginalStructure",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Acknowledge",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "ResponseType",
            "in": "query",
            "schema": {
              "$ref": "#/components/schemas/Sales.ResponseTypeType"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrderSearch"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrderSearch"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrderSearch"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Search/Next/{id}": {
      "get": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "5a898bbc-cabe-4b8d-ba2f-8eb2b9942fbe",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "put": {
        "tags": [
          "SalesOrder"
        ],
        "operationId": "5a898bbc-cabe-4b8d-ba2f-8eb2b9942fbe",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{id}/Documents": {
      "get": {
        "tags": [
          "SalesOrderDocument"
        ],
        "operationId": "994c9ee6-3d9d-4017-9ffe-cefd3ac51b10",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SalesOrderDocument"
        ],
        "operationId": "fc203f1b-0fde-441f-97e1-de1458238fc2",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Base.Document"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Base.Document"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Base.Document"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/Documents": {
      "get": {
        "tags": [
          "SalesOrderDocument"
        ],
        "operationId": "cb81aaf8-5a72-49bf-ae6e-286661e9378e",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SalesOrderDocument"
        ],
        "operationId": "e2c1c34e-0427-42c2-b145-87def292e456",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Base.Document"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Base.Document"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Base.Document"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{id}/Documents/{trackingNumber}": {
      "get": {
        "tags": [
          "SalesOrderDocument"
        ],
        "operationId": "7c44b88f-2a17-4d63-aa66-d273ef0c4758",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "trackingNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/{id}/Fulfillments": {
      "get": {
        "tags": [
          "SalesOrderFulfillment"
        ],
        "operationId": "0b583487-58a4-416b-a3b4-6842c764bd4a",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/PurchaseOrder/Channel/{channelId}/{orderNumber}/Fulfillments": {
      "get": {
        "tags": [
          "SalesOrderFulfillment"
        ],
        "operationId": "f6348931-52bb-49c7-b5b3-f9b778728c0b",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{id}/Fulfillments": {
      "get": {
        "tags": [
          "SalesOrderFulfillments"
        ],
        "operationId": "b17806d5-af86-4173-85eb-8687a5a59d09",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}/Items": {
      "get": {
        "tags": [
          "SalesOrderItem"
        ],
        "operationId": "b9630aea-bb1e-45a7-b851-693995a965b3",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SalesOrderItem"
        ],
        "operationId": "557ec2e0-3511-4a4a-9130-29d81c45760f",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Sales.SalesOrderItem"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Sales.SalesOrderItem"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Sales.SalesOrderItem"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/Items": {
      "get": {
        "tags": [
          "SalesOrderItem"
        ],
        "operationId": "1407dc3a-4e25-41bd-9592-f71f5780c9d0",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SalesOrderItem"
        ],
        "operationId": "4ce13efd-9983-4d6c-adcf-413cc4be4b59",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Sales.SalesOrderItem"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Sales.SalesOrderItem"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Sales.SalesOrderItem"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}/Items/{itemId}": {
      "put": {
        "tags": [
          "SalesOrderItem"
        ],
        "operationId": "c764e756-eb1a-4235-8ed9-058559a50336",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "itemId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrderItem"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrderItem"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrderItem"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "delete": {
        "tags": [
          "SalesOrderItem"
        ],
        "operationId": "8f872c04-3a5a-488e-82c5-851643edc10e",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "itemId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/Items/{itemId}": {
      "put": {
        "tags": [
          "SalesOrderItem"
        ],
        "operationId": "f02e3c37-07f1-4164-bc65-eb24a5023569",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "itemId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrderItem"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrderItem"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Sales.SalesOrderItem"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "delete": {
        "tags": [
          "SalesOrderItem"
        ],
        "operationId": "d97fd833-b9d7-4061-807f-e8558756ebb8",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "itemId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}/Items/{lineNumber}/Options": {
      "get": {
        "tags": [
          "SalesOrderItemOptions"
        ],
        "operationId": "c0c8ecde-57c6-467c-8b54-4798736392d1",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "lineNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SalesOrderItemOptions"
        ],
        "operationId": "73560a1e-e98a-48b1-8d06-da95fdd1ef2a",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "lineNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "put": {
        "tags": [
          "SalesOrderItemOptions"
        ],
        "operationId": "d4e5eb09-5c18-4898-a946-a31f55ac2404",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "lineNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/Items/{lineNumber}/Options": {
      "get": {
        "tags": [
          "SalesOrderItemOptions"
        ],
        "operationId": "f509f747-ad0d-4544-9fef-1f8021dadaff",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "lineNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SalesOrderItemOptions"
        ],
        "operationId": "86b3dc1e-7405-4053-ac2e-c88481559294",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "lineNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "put": {
        "tags": [
          "SalesOrderItemOptions"
        ],
        "operationId": "bfba3a41-cfab-4a9a-aa25-a9f18f52d23d",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "lineNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}/Items/{lineNumber}/Options/{optionId}": {
      "delete": {
        "tags": [
          "SalesOrderItemOptions"
        ],
        "operationId": "1d321c3d-e86d-4862-986b-dbace3166379",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "lineNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          },
          {
            "name": "optionId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}/Options": {
      "get": {
        "tags": [
          "SalesOrderOptions"
        ],
        "operationId": "7fd310da-7937-4fd2-b9ae-e3874da84938",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SalesOrderOptions"
        ],
        "operationId": "dda13ea9-627a-430c-8248-6f7232eb53ad",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "put": {
        "tags": [
          "SalesOrderOptions"
        ],
        "operationId": "c74ae60d-ba09-4ed6-b8a4-5ec7b88133e7",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/Options": {
      "get": {
        "tags": [
          "SalesOrderOptions"
        ],
        "operationId": "4cb35c8d-c6ee-4196-8fef-34561892d9ab",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SalesOrderOptions"
        ],
        "operationId": "c78c8eff-34e7-4c6c-8616-e940756abeac",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "put": {
        "tags": [
          "SalesOrderOptions"
        ],
        "operationId": "bde07a26-47bb-4b56-8db3-659caf1f2893",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/Order.OrderOption"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{orderId}/Options/{optionId}": {
      "delete": {
        "tags": [
          "SalesOrderOptions"
        ],
        "operationId": "50faa003-f177-4e7a-9937-e4190deefce0",
        "parameters": [
          {
            "name": "orderId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "optionId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{id}/Shipments": {
      "get": {
        "tags": [
          "SalesOrderShipment"
        ],
        "operationId": "dbd0694b-3bec-4559-be68-dbc15faa9b6c",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SalesOrderShipment"
        ],
        "operationId": "17c5940a-06d0-4432-92c7-14242de489fa",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "put": {
        "tags": [
          "SalesOrderShipment"
        ],
        "operationId": "b60ddfdf-0882-412b-a08e-fc1a56bcb432",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/Channel/{channelId}/{orderNumber}/Shipments": {
      "get": {
        "tags": [
          "SalesOrderShipment"
        ],
        "operationId": "c33e1b48-613c-469f-b853-064803c5024a",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SalesOrderShipment"
        ],
        "operationId": "7dc2ab61-0d64-4cd4-8301-bb423d592d0c",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "orderNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/SalesOrder/{id}/Shipments/{shipmentId}": {
      "put": {
        "tags": [
          "SalesOrderShipment"
        ],
        "operationId": "1d08e56e-ebf0-4df2-9de6-ef0237dc1491",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "shipmentId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Order.Shipment"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Shipping/Label/{trackingNumber}": {
      "get": {
        "tags": [
          "Shipping"
        ],
        "operationId": "fbcc941a-aaff-48ed-9a2f-7ed919a683ae",
        "parameters": [
          {
            "name": "trackingNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "delete": {
        "tags": [
          "Shipping"
        ],
        "operationId": "5e87efb5-82d1-42c4-8895-84fd93bb4432",
        "parameters": [
          {
            "name": "trackingNumber",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Shipping/Label": {
      "put": {
        "tags": [
          "Shipping"
        ],
        "operationId": "500f119d-a193-4e70-9de8-f6bd65a86034",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/Shipping.Request"
              }
            },
            "text/json": {
              "schema": {
                "$ref": "#/components/schemas/Shipping.Request"
              }
            },
            "application/*+json": {
              "schema": {
                "$ref": "#/components/schemas/Shipping.Request"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/CatalogSource/{sourceId}/SourceItems": {
      "get": {
        "tags": [
          "SourceItem"
        ],
        "operationId": "2acf8340-dc35-4e12-8d48-6823f5eb8bfa",
        "parameters": [
          {
            "name": "sourceId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "IncludeData",
            "in": "query",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "Page",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          },
          {
            "name": "PageSize",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          },
          {
            "name": "Skip",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "delete": {
        "tags": [
          "SourceItem"
        ],
        "operationId": "02294c5f-8edd-45c0-b304-6f8220709324",
        "parameters": [
          {
            "name": "sourceId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      },
      "post": {
        "tags": [
          "SourceItem"
        ],
        "operationId": "0c41d93c-c134-4d84-9c72-e269aa48ce4e",
        "parameters": [
          {
            "name": "sourceId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/CatalogSource.SourceItem"
                }
              }
            },
            "text/json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/CatalogSource.SourceItem"
                }
              }
            },
            "application/*+json": {
              "schema": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/CatalogSource.SourceItem"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Connect": {
      "get": {
        "tags": [
          "System"
        ],
        "operationId": "17f81002-8ceb-40c3-a0b1-91f3ec6af5e3",
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/System/Configuration": {
      "get": {
        "tags": [
          "System"
        ],
        "operationId": "22e39e78-6b17-4e13-b6f2-334d922c3fae",
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/System/PackageType": {
      "get": {
        "tags": [
          "System"
        ],
        "operationId": "b6bdbca8-a948-4f41-af50-441cab6f9815",
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/System/Carrier": {
      "get": {
        "tags": [
          "System"
        ],
        "operationId": "f395a360-516a-483f-aa47-6c58346dc803",
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/System/ReasonCode": {
      "get": {
        "tags": [
          "System"
        ],
        "operationId": "c02a379b-3782-41b0-90b7-ef5b31fd74ef",
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/System/Channel": {
      "get": {
        "tags": [
          "System"
        ],
        "operationId": "c697a53f-d0ae-480e-8312-960ee14e52a7",
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/System/Filters": {
      "get": {
        "tags": [
          "System"
        ],
        "operationId": "067f00f0-7720-49c6-8f99-11cb30a03ff1",
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/System/Channel/{channelId}": {
      "get": {
        "tags": [
          "System"
        ],
        "operationId": "39fbdc1f-db7d-477d-838c-79af8a361a9c",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/System/Check": {
      "get": {
        "tags": [
          "System"
        ],
        "operationId": "503a31cd-042f-47a5-9d33-d2b40e040177",
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/System/Logging/{level}": {
      "put": {
        "tags": [
          "System"
        ],
        "operationId": "0544f189-14b2-49c0-814a-85b49d660512",
        "parameters": [
          {
            "name": "level",
            "in": "path",
            "required": true,
            "schema": {
              "$ref": "#/components/schemas/Process.LoggingLevelType"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Taxonomy": {
      "get": {
        "tags": [
          "Taxonomy"
        ],
        "operationId": "6df73e85-8bb7-4586-9ae8-1924af7e4e8d",
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Taxonomy/{id}": {
      "get": {
        "tags": [
          "Taxonomy"
        ],
        "operationId": "e9086a48-e4c1-42f2-91b6-473c8603f1fa",
        "parameters": [
          {
            "name": "id",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Taxonomy/Channel/{channelId}": {
      "get": {
        "tags": [
          "Taxonomy"
        ],
        "operationId": "d7087cb6-a394-46e4-a947-aec2d6f955fe",
        "parameters": [
          {
            "name": "channelId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    },
    "/api/Taxonomy/{taxonomyId}/Category/{categoryCode}/{includeChildren}": {
      "get": {
        "tags": [
          "Taxonomy"
        ],
        "operationId": "2552fa08-c3d6-41c9-8089-9df229a317b6",
        "parameters": [
          {
            "name": "taxonomyId",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "format": "uuid"
            }
          },
          {
            "name": "categoryCode",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "includeChildren",
            "in": "path",
            "required": true,
            "schema": {
              "type": "boolean"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "OK"
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "Base.DateRange": {
        "type": "object",
        "properties": {
          "FromDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "ToDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "HasValue": {
            "type": "boolean",
            "readOnly": true
          }
        },
        "additionalProperties": false
      },
      "Base.Document": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "ShipmentId": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "DocumentNumber": {
            "type": "string",
            "nullable": true
          },
          "DocumentImage": {
            "type": "string",
            "format": "byte",
            "nullable": true
          },
          "DocumentFormat": {
            "$ref": "#/components/schemas/Base.DocumentFormatType"
          },
          "DocumentType": {
            "$ref": "#/components/schemas/Order.DocumentTypeType"
          },
          "Orientation": {
            "$ref": "#/components/schemas/Base.OrientationType"
          },
          "PageSize": {
            "$ref": "#/components/schemas/Units.PageSize"
          }
        },
        "additionalProperties": false
      },
      "Base.DocumentFormatType": {
        "enum": [
          "None",
          "PNG",
          "PDF",
          "ZPL"
        ],
        "type": "string"
      },
      "Base.Identifier": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "Code": {
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Base.OrientationType": {
        "enum": [
          "NotSpecified",
          "Portrait",
          "Landscape"
        ],
        "type": "string"
      },
      "Catalog.Item.ItemType": {
        "enum": [
          "Item",
          "Group",
          "Variant",
          "Kit",
          "Assembly",
          "Virtual",
          "NonStock",
          "Service",
          "Component"
        ],
        "type": "string"
      },
      "CatalogSource.Column": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "Sequence": {
            "type": "integer",
            "format": "int32"
          },
          "Name": {
            "type": "string",
            "nullable": true
          },
          "SourceName": {
            "type": "string",
            "nullable": true
          },
          "SourceSequence": {
            "type": "integer",
            "format": "int32"
          },
          "StartPosition": {
            "type": "integer",
            "format": "int32"
          },
          "FieldLength": {
            "type": "integer",
            "format": "int32"
          },
          "DataType": {
            "$ref": "#/components/schemas/CatalogSource.ColumnDataTypeType"
          },
          "MaxLength": {
            "type": "integer",
            "format": "int32"
          },
          "Ignore": {
            "type": "boolean"
          },
          "HasUniqueValues": {
            "type": "boolean"
          },
          "UniqueValues": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/CatalogSource.UniqueValue"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "CatalogSource.ColumnDataTypeType": {
        "enum": [
          "Undefined",
          "String",
          "Number",
          "Date",
          "Json"
        ],
        "type": "string"
      },
      "CatalogSource.MapTypeType": {
        "enum": [
          "None",
          "Sku",
          "MasterSku",
          "Title",
          "UomQuantity",
          "UomCode",
          "Cartonization",
          "Manufacturer",
          "MfrPartNo",
          "MfrAbbr",
          "MfrNameMap",
          "MfrCode",
          "Identifier",
          "Attribute",
          "Category",
          "ProductType",
          "Status",
          "ListingState",
          "ItemType",
          "Condition",
          "PhysicalLocation",
          "VariationValue",
          "VariationCodes",
          "ComponentSku",
          "ComponentQuantity",
          "Parent",
          "ReviewStatus",
          "AvailabilityMode",
          "PublicationMode",
          "FulfillmentMethod",
          "FulfillmentMode",
          "FulfillmentLatency",
          "RelationshipSku",
          "RelationshipType",
          "RelationshipPriority",
          "RelationshipQuantity",
          "RelationshipValue",
          "Cost",
          "Price",
          "Msrp",
          "Map",
          "Upp",
          "Shipping",
          "Handling",
          "AdditionalCharge",
          "ExpireMap",
          "ExpireUpp",
          "ExpireMsrp",
          "Weight",
          "Width",
          "Length",
          "Height",
          "AutoShippingPolicyFlag",
          "ShippingPolicyName",
          "PublicationTemplateName",
          "ReplenishmentEnabled",
          "ReplenishmentMin",
          "ReplenighmentMax",
          "MinimumOrderQuantity",
          "MaximumOrderQuantity",
          "HarmonizedTariffCode",
          "CountryOfOrigin",
          "Buyer",
          "Image",
          "Ormd",
          "PricePolicy",
          "AutomaticPricingPolicy",
          "PriceBand",
          "AutomaticPricing",
          "Quantity",
          "Latency",
          "Validation",
          "Custom",
          "Analysis",
          "Media"
        ],
        "type": "string"
      },
      "CatalogSource.SourceItem": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid"
          },
          "Sku": {
            "type": "string",
            "nullable": true
          },
          "ItemType": {
            "$ref": "#/components/schemas/Catalog.Item.ItemType"
          },
          "Data": {
            "type": "object",
            "additionalProperties": {
              "$ref": "#/components/schemas/Newtonsoft.Json.Linq.JToken"
            },
            "nullable": true
          },
          "LineNum": {
            "type": "integer",
            "format": "int32",
            "nullable": true
          },
          "MasterSku": {
            "type": "string",
            "nullable": true
          },
          "AnalysisStatus": {
            "type": "string",
            "nullable": true
          },
          "AnalysisMessage": {
            "type": "string",
            "nullable": true
          },
          "MatchType": {
            "type": "string",
            "nullable": true
          },
          "LoadedDate": {
            "type": "string",
            "format": "date-time"
          },
          "AnalizedDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "UpdatedDate": {
            "type": "string",
            "format": "date-time"
          }
        },
        "additionalProperties": false
      },
      "CatalogSource.UniqueValue": {
        "type": "object",
        "properties": {
          "Value": {
            "type": "string",
            "nullable": true
          },
          "Count": {
            "type": "integer",
            "format": "int32"
          },
          "Action": {
            "$ref": "#/components/schemas/CatalogSource.UniqueValue+ActionType"
          }
        },
        "additionalProperties": false
      },
      "CatalogSource.UniqueValue+ActionType": {
        "enum": [
          "None",
          "Exclude",
          "Include"
        ],
        "type": "string"
      },
      "Channel.LocationIdentifer": {
        "type": "object",
        "properties": {
          "Channel": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "Location": {
            "$ref": "#/components/schemas/Base.Identifier"
          }
        },
        "additionalProperties": false
      },
      "Contact.Address": {
        "type": "object",
        "properties": {
          "Line1": {
            "type": "string",
            "nullable": true
          },
          "Line2": {
            "type": "string",
            "nullable": true
          },
          "Line3": {
            "type": "string",
            "nullable": true
          },
          "City": {
            "type": "string",
            "nullable": true
          },
          "StateRegion": {
            "type": "string",
            "nullable": true
          },
          "PostalCode": {
            "type": "string",
            "nullable": true
          },
          "CountryCode": {
            "type": "string",
            "nullable": true
          },
          "Phone": {
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Contact.Contact": {
        "type": "object",
        "properties": {
          "FirstName": {
            "type": "string",
            "nullable": true
          },
          "LastName": {
            "type": "string",
            "nullable": true
          },
          "FullName": {
            "type": "string",
            "nullable": true
          },
          "CompanyName": {
            "type": "string",
            "nullable": true
          },
          "Email": {
            "type": "string",
            "nullable": true
          },
          "Phone": {
            "type": "string",
            "nullable": true
          },
          "Address": {
            "$ref": "#/components/schemas/Contact.Address"
          }
        },
        "additionalProperties": false
      },
      "Customer.Fulfillment": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid"
          },
          "SalesOrderId": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "FulfillmentOrderId": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "FulfillmentLocationCode": {
            "type": "string",
            "nullable": true
          },
          "SourceLocationCode": {
            "type": "string",
            "nullable": true
          },
          "PackageTypeCode": {
            "type": "string",
            "nullable": true
          },
          "FulfillmentMethod": {
            "$ref": "#/components/schemas/Customer.FulfillmentMethodType"
          },
          "Carrier": {
            "type": "string",
            "nullable": true
          },
          "CarrierServiceLevel": {
            "type": "string",
            "nullable": true
          },
          "EstimatedShippingCost": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "PackagingCost": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Weight": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "WeightUnit": {
            "$ref": "#/components/schemas/Units.WeightUnitType"
          },
          "Length": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Width": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Height": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "DimensionUnit": {
            "$ref": "#/components/schemas/Units.DimensionUnitType"
          },
          "PlannedShipDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "EstimatedDeliveryDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "Items": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Customer.FulfillmentItem"
            },
            "nullable": true
          },
          "Shipments": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Order.Shipment"
            },
            "nullable": true
          },
          "FulfillmentCodes": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Customer.FulfillmentCode"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Customer.FulfillmentCode": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "ChannelId": {
            "type": "string",
            "format": "uuid"
          },
          "ChannelName": {
            "type": "string",
            "nullable": true
          },
          "Code": {
            "type": "string",
            "nullable": true
          },
          "Status": {
            "$ref": "#/components/schemas/Customer.FulfillmentStatusType"
          },
          "StatusNote": {
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Customer.FulfillmentItem": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid"
          },
          "SalesOrderItemId": {
            "type": "string",
            "format": "uuid"
          },
          "Quantity": {
            "type": "number",
            "format": "double"
          },
          "Ordered": {
            "type": "number",
            "format": "double"
          },
          "PackageTypeId": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "FulfillmentMethod": {
            "$ref": "#/components/schemas/Customer.FulfillmentMethodType"
          },
          "CarrierServiceLevelId": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Customer.FulfillmentMethodType": {
        "enum": [
          "None",
          "Direct",
          "Dropship",
          "CrossDock",
          "ThreePl",
          "All"
        ],
        "type": "string"
      },
      "Customer.FulfillmentStatusType": {
        "enum": [
          "None",
          "New",
          "Complete",
          "Error"
        ],
        "type": "string"
      },
      "Inventory.Adjustment.Adjustment": {
        "type": "object",
        "properties": {
          "Notes": {
            "type": "string",
            "nullable": true
          },
          "ReferenceDoc": {
            "type": "string",
            "nullable": true
          },
          "LocationId": {
            "type": "string",
            "format": "uuid"
          },
          "ReasonCode": {
            "type": "string",
            "nullable": true
          },
          "Items": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Inventory.Item"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Inventory.Assembly.Assembly": {
        "type": "object",
        "properties": {
          "Notes": {
            "type": "string",
            "nullable": true
          },
          "ReferenceDoc": {
            "type": "string",
            "nullable": true
          },
          "ToLocationId": {
            "type": "string",
            "format": "uuid"
          },
          "FromLocationId": {
            "type": "string",
            "format": "uuid"
          },
          "ReasonCode": {
            "type": "string",
            "nullable": true
          },
          "AssemblyNumber": {
            "type": "string",
            "nullable": true
          },
          "AssemblySku": {
            "type": "string",
            "nullable": true
          },
          "Quantity": {
            "type": "integer",
            "format": "int32"
          }
        },
        "additionalProperties": false
      },
      "Inventory.AvailableQuantity": {
        "type": "object",
        "properties": {
          "Quantity": {
            "type": "integer",
            "format": "int32"
          },
          "Latency": {
            "type": "integer",
            "format": "int32",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Inventory.EventSearch": {
        "type": "object",
        "properties": {
          "PageSize": {
            "type": "integer",
            "format": "int32"
          },
          "Background": {
            "type": "boolean"
          },
          "Location": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "EventType": {
            "$ref": "#/components/schemas/Inventory.InventoryEventType"
          },
          "EventDate": {
            "$ref": "#/components/schemas/Base.DateRange"
          },
          "NewOnly": {
            "type": "boolean",
            "nullable": true
          },
          "HasValue": {
            "type": "boolean",
            "readOnly": true
          }
        },
        "additionalProperties": false
      },
      "Inventory.InventoryEventType": {
        "enum": [
          "Receive",
          "Ship",
          "VoidShipment",
          "Transfer",
          "Absolute",
          "Adjust",
          "Reset",
          "AverageCost",
          "Assembly",
          "Disassembly"
        ],
        "type": "string"
      },
      "Inventory.Item": {
        "type": "object",
        "properties": {
          "ItemId": {
            "type": "string",
            "format": "uuid"
          },
          "Quantity": {
            "type": "integer",
            "format": "int32"
          },
          "UomQuantity": {
            "type": "number",
            "format": "double"
          },
          "Value": {
            "type": "number",
            "format": "double"
          }
        },
        "additionalProperties": false
      },
      "Inventory.PutAway.PutAwayRequest": {
        "type": "object",
        "properties": {
          "Search": {
            "type": "string",
            "nullable": true
          },
          "StorageLocationId": {
            "type": "string",
            "format": "uuid"
          },
          "PutAwayLocationId": {
            "type": "string",
            "format": "uuid"
          }
        },
        "additionalProperties": false
      },
      "Inventory.Transfer.Transfer": {
        "type": "object",
        "properties": {
          "Notes": {
            "type": "string",
            "nullable": true
          },
          "ReferenceDoc": {
            "type": "string",
            "nullable": true
          },
          "FromLocationId": {
            "type": "string",
            "format": "uuid"
          },
          "ToLocationId": {
            "type": "string",
            "format": "uuid"
          },
          "ReasonCode": {
            "type": "string",
            "nullable": true
          },
          "Items": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Inventory.Item"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Microsoft.AspNetCore.Mvc.ProblemDetails": {
        "type": "object",
        "properties": {
          "type": {
            "type": "string",
            "nullable": true
          },
          "title": {
            "type": "string",
            "nullable": true
          },
          "status": {
            "type": "integer",
            "format": "int32",
            "nullable": true
          },
          "detail": {
            "type": "string",
            "nullable": true
          },
          "instance": {
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": {}
      },
      "Newtonsoft.Json.Linq.JToken": {
        "type": "array",
        "items": {
          "$ref": "#/components/schemas/Newtonsoft.Json.Linq.JToken"
        }
      },
      "Order.DocumentTypeType": {
        "enum": [
          "None",
          "PackingSlip",
          "BillofLading",
          "Shipping"
        ],
        "type": "string"
      },
      "Order.OrderCode": {
        "type": "object",
        "properties": {
          "Channel": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "ModifiedDate": {
            "type": "string",
            "format": "date-time"
          },
          "Status": {
            "$ref": "#/components/schemas/Order.OrderStatus"
          },
          "OrderNumber": {
            "type": "string",
            "nullable": true
          },
          "Notes": {
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Order.OrderItemIdentifier": {
        "type": "object",
        "properties": {
          "OrderType": {
            "$ref": "#/components/schemas/Order.OrderItemIdentifier+OrderTypeValue"
          },
          "OrderId": {
            "type": "string",
            "format": "uuid"
          },
          "OrderStatus": {
            "type": "string",
            "nullable": true
          },
          "LineNumber": {
            "type": "integer",
            "format": "int32"
          }
        },
        "additionalProperties": false
      },
      "Order.OrderItemIdentifier+OrderTypeValue": {
        "enum": [
          "None",
          "Sales",
          "Purchase",
          "Work"
        ],
        "type": "string"
      },
      "Order.OrderOption": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "Code": {
            "type": "string",
            "nullable": true
          },
          "Value": {
            "type": "string",
            "nullable": true
          },
          "Channel": {
            "$ref": "#/components/schemas/Base.Identifier"
          }
        },
        "additionalProperties": false
      },
      "Order.OrderStatus": {
        "enum": [
          "New",
          "Open",
          "Cancelled",
          "Partial",
          "Acknowledged",
          "Fulfilled",
          "Completed",
          "Invoiced",
          "Paid",
          "Refunded",
          "Unknown"
        ],
        "type": "string"
      },
      "Order.Shipment": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid"
          },
          "TrackingNumber": {
            "type": "string",
            "nullable": true
          },
          "Carrier": {
            "type": "string",
            "nullable": true
          },
          "CarrierServiceLevel": {
            "type": "string",
            "nullable": true
          },
          "Fulfillment": {
            "$ref": "#/components/schemas/Customer.Fulfillment"
          },
          "Status": {
            "$ref": "#/components/schemas/Shipping.ShipmentStatusType"
          },
          "StatusNote": {
            "type": "string",
            "nullable": true
          },
          "StatusDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "Label": {
            "$ref": "#/components/schemas/Shipping.Label"
          },
          "DateShipped": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "PackageTypeCode": {
            "type": "string",
            "nullable": true
          },
          "PackageWeight": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "PackageLength": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "PackageWidth": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "PackageHeight": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "WeightUnit": {
            "$ref": "#/components/schemas/Units.WeightUnitType"
          },
          "DimensionUnit": {
            "$ref": "#/components/schemas/Units.DimensionUnitType"
          },
          "ShippingCost": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "CurrencyCode": {
            "type": "string",
            "nullable": true
          },
          "Items": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Order.ShipmentItem"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Order.ShipmentItem": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "LineNum": {
            "type": "integer",
            "format": "int32"
          },
          "Sku": {
            "type": "string",
            "nullable": true
          },
          "MasterSku": {
            "type": "string",
            "nullable": true
          },
          "UomCode": {
            "type": "string",
            "nullable": true
          },
          "UomQuantity": {
            "type": "integer",
            "format": "int32"
          },
          "Shipped": {
            "type": "integer",
            "format": "int32"
          },
          "Lots": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Order.ShippedLot"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Order.ShippedLot": {
        "type": "object",
        "properties": {
          "LotNumber": {
            "type": "string",
            "nullable": true
          },
          "ExpirationDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "Shipped": {
            "type": "number",
            "format": "double"
          }
        },
        "additionalProperties": false
      },
      "Process.LoggingLevelType": {
        "enum": [
          "None",
          "Critical",
          "Error",
          "Warning",
          "Information",
          "Debug"
        ],
        "type": "string"
      },
      "Process.RemoteJobStatus": {
        "enum": [
          "None",
          "Submitted",
          "Aborted",
          "Failed",
          "Ready",
          "Complete",
          "Expired",
          "Executing",
          "NoData"
        ],
        "type": "string"
      },
      "Sales.FulfillmentAssignment": {
        "type": "object",
        "properties": {
          "FulfillmentLocationId": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "FulfillmentMethod": {
            "$ref": "#/components/schemas/Customer.FulfillmentMethodType"
          },
          "ReleaseDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "Hold": {
            "type": "boolean",
            "nullable": true
          },
          "Review": {
            "type": "boolean",
            "nullable": true
          },
          "AutoCartonization": {
            "type": "boolean",
            "nullable": true
          },
          "RemovePackaging": {
            "type": "boolean",
            "nullable": true
          },
          "SendFulfillment": {
            "type": "boolean",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Sales.FulfillmentOverride": {
        "type": "object",
        "properties": {
          "Method": {
            "$ref": "#/components/schemas/Customer.FulfillmentMethodType"
          },
          "ShippingFromLocation": {
            "$ref": "#/components/schemas/Channel.LocationIdentifer"
          }
        },
        "additionalProperties": false
      },
      "Sales.HoldCode": {
        "type": "object",
        "properties": {
          "Code": {
            "type": "string",
            "nullable": true
          },
          "Name": {
            "type": "string",
            "nullable": true
          },
          "StartTime": {
            "type": "string",
            "format": "date-time"
          },
          "EndTime": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Sales.PurchaseAllocation": {
        "type": "object",
        "properties": {
          "PurchaseOrderItem": {
            "$ref": "#/components/schemas/Order.OrderItemIdentifier"
          },
          "Quantity": {
            "type": "number",
            "format": "double"
          },
          "Notes": {
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Sales.ResponseTypeType": {
        "enum": [
          "Simple",
          "Full",
          "Shipment"
        ],
        "type": "string"
      },
      "Sales.SalesOrder": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "SalesChannel": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "OrderNumber": {
            "type": "string",
            "nullable": true
          },
          "SalesOrderNumber": {
            "type": "string",
            "nullable": true
          },
          "OrderDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "Currency": {
            "type": "string",
            "nullable": true
          },
          "Customer": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "ReleaseDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "EarliestShipDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "Shipping": {
            "$ref": "#/components/schemas/Sales.SalesOrderShippingDetails"
          },
          "FulfillmentOverride": {
            "$ref": "#/components/schemas/Sales.FulfillmentOverride"
          },
          "ShipTo": {
            "$ref": "#/components/schemas/Sales.SalesOrderAddress"
          },
          "BillTo": {
            "$ref": "#/components/schemas/Sales.SalesOrderAddress"
          },
          "Status": {
            "$ref": "#/components/schemas/Order.OrderStatus"
          },
          "ChannelCodes": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Order.OrderCode"
            },
            "nullable": true
          },
          "HoldCodes": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Sales.HoldCode"
            },
            "nullable": true
          },
          "Items": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Sales.SalesOrderItem"
            },
            "nullable": true
          },
          "Options": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Order.OrderOption"
            },
            "nullable": true
          },
          "Promotions": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Sales.SalesOrderPromotion"
            },
            "nullable": true
          },
          "Shipments": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Order.Shipment"
            },
            "nullable": true
          },
          "Documents": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Base.Document"
            },
            "nullable": true
          },
          "OrderSummary": {
            "$ref": "#/components/schemas/Sales.SalesOrder+OrderSummaryType"
          }
        },
        "additionalProperties": false
      },
      "Sales.SalesOrder+OrderSummaryType": {
        "type": "object",
        "properties": {
          "TotalSales": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "TotalSalesTax": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "TotalDiscount": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "TotalShipping": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "TotalShippingTax": {
            "type": "number",
            "format": "double",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Sales.SalesOrderAddress": {
        "type": "object",
        "properties": {
          "FirstName": {
            "type": "string",
            "nullable": true
          },
          "LastName": {
            "type": "string",
            "nullable": true
          },
          "FullName": {
            "type": "string",
            "nullable": true
          },
          "CompanyName": {
            "type": "string",
            "nullable": true
          },
          "Street1": {
            "type": "string",
            "nullable": true
          },
          "Street2": {
            "type": "string",
            "nullable": true
          },
          "City": {
            "type": "string",
            "nullable": true
          },
          "StateRegion": {
            "type": "string",
            "nullable": true
          },
          "Postal": {
            "type": "string",
            "nullable": true
          },
          "Country": {
            "type": "string",
            "nullable": true
          },
          "CountryCode": {
            "type": "string",
            "nullable": true
          },
          "Email": {
            "type": "string",
            "nullable": true
          },
          "Phone": {
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Sales.SalesOrderItem": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "AutoCreate": {
            "type": "boolean",
            "nullable": true
          },
          "LineNum": {
            "type": "integer",
            "format": "int32"
          },
          "ChannelLineNum": {
            "type": "string",
            "nullable": true
          },
          "MasterSku": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "ChannelSku": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "Sku": {
            "type": "string",
            "nullable": true
          },
          "UomCode": {
            "type": "string",
            "nullable": true
          },
          "UomQuantity": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Price": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Shipping": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Tax": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "ShippingTax": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Ordered": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Shipped": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "FulfillmentLocation": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "FulfillmentMethod": {
            "$ref": "#/components/schemas/Customer.FulfillmentMethodType"
          },
          "Allocated": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Options": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Order.OrderOption"
            },
            "nullable": true
          },
          "PurchaseAllocations": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Sales.PurchaseAllocation"
            },
            "nullable": true
          },
          "KitItems": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Sales.SalesOrderItem"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Sales.SalesOrderPromotion": {
        "type": "object",
        "properties": {
          "Benefits": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Sales.SalesOrderPromotion+SalesOrderBenefit"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Sales.SalesOrderPromotion+SalesOrderBenefit": {
        "type": "object",
        "properties": {
          "Discount": {
            "type": "number",
            "format": "double"
          }
        },
        "additionalProperties": false
      },
      "Sales.SalesOrderSearch": {
        "type": "object",
        "properties": {
          "FilterId": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "SalesChannelId": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "SalesChannel": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "Status": {
            "type": "string",
            "nullable": true
          },
          "HoldCodes": {
            "type": "array",
            "items": {
              "type": "string"
            },
            "nullable": true
          },
          "PageSize": {
            "type": "integer",
            "format": "int32"
          },
          "Background": {
            "type": "boolean"
          },
          "OrderDate": {
            "$ref": "#/components/schemas/Base.DateRange"
          },
          "ModifiedDate": {
            "$ref": "#/components/schemas/Base.DateRange"
          },
          "ShippedDate": {
            "$ref": "#/components/schemas/Base.DateRange"
          },
          "OrderModified": {
            "type": "boolean"
          },
          "UseModifiedSearch": {
            "type": "boolean",
            "readOnly": true
          },
          "ShipmentModified": {
            "type": "boolean"
          },
          "ShipmentStatus": {
            "$ref": "#/components/schemas/Shipping.ShipmentStatusType"
          },
          "FulfillmentLocationId": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "HasValue": {
            "type": "boolean",
            "readOnly": true
          }
        },
        "additionalProperties": false
      },
      "Sales.SalesOrderShippingDetails": {
        "type": "object",
        "properties": {
          "ShippingServiceLevel": {
            "type": "string",
            "nullable": true
          },
          "FulfillmentServiceLevel": {
            "type": "string",
            "nullable": true
          },
          "ShippingCost": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "ShipByDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "DeliverByDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Shipping.Label": {
        "type": "object",
        "properties": {
          "TrackingNumber": {
            "type": "string",
            "nullable": true
          },
          "Carrier": {
            "type": "string",
            "nullable": true
          },
          "ServiceLevel": {
            "type": "string",
            "nullable": true
          },
          "Cost": {
            "type": "number",
            "format": "double"
          },
          "EstimatedDeliveryDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "LabelFormat": {
            "$ref": "#/components/schemas/Base.DocumentFormatType"
          },
          "LabelData": {
            "type": "string",
            "format": "byte",
            "nullable": true
          },
          "ShippedDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "DeliveredDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "Voided": {
            "type": "boolean"
          },
          "Status": {
            "$ref": "#/components/schemas/Shipping.ShipmentStatusType"
          },
          "StatusDate": {
            "type": "string",
            "format": "date-time"
          }
        },
        "additionalProperties": false
      },
      "Shipping.Request": {
        "type": "object",
        "properties": {
          "ShipFromLocationCode": {
            "type": "string",
            "nullable": true
          },
          "ShipDocumentType": {
            "$ref": "#/components/schemas/Shipping.Request+ShipDocumentTypeType"
          },
          "ShipDocumentNumber": {
            "type": "string",
            "nullable": true
          },
          "Type": {
            "$ref": "#/components/schemas/Shipping.Request+RequestType"
          },
          "Function": {
            "$ref": "#/components/schemas/Shipping.Request+FunctionType"
          },
          "LabelFormat": {
            "$ref": "#/components/schemas/Base.DocumentFormatType"
          },
          "ShippingServiceName": {
            "type": "string",
            "nullable": true
          },
          "ServiceLevel": {
            "type": "string",
            "nullable": true
          },
          "ShipTo": {
            "$ref": "#/components/schemas/Contact.Address"
          },
          "Weight": {
            "$ref": "#/components/schemas/Units.WeightType"
          },
          "Items": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Shipping.RequestItem"
            },
            "nullable": true
          },
          "Reference": {
            "type": "string",
            "nullable": true
          },
          "SelectedId": {
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Shipping.Request+FunctionType": {
        "enum": [
          "Rate",
          "Ship",
          "RateAndShip"
        ],
        "type": "string"
      },
      "Shipping.Request+RequestType": {
        "enum": [
          "Ship",
          "Return"
        ],
        "type": "string"
      },
      "Shipping.Request+ShipDocumentTypeType": {
        "enum": [
          "None",
          "SalesOrder",
          "PurchaseOrder"
        ],
        "type": "string"
      },
      "Shipping.RequestItem": {
        "type": "object",
        "properties": {
          "Sku": {
            "type": "string",
            "nullable": true
          },
          "Quantity": {
            "type": "integer",
            "format": "int32"
          }
        },
        "additionalProperties": false
      },
      "Shipping.ShipmentStatusType": {
        "enum": [
          "None",
          "Created",
          "Shipped",
          "Accepted",
          "InTransit",
          "Delivered",
          "Exception",
          "Void"
        ],
        "type": "string"
      },
      "Supplier.ItemReceipt": {
        "type": "object",
        "properties": {
          "Quantity": {
            "type": "number",
            "format": "double"
          },
          "Date": {
            "type": "string",
            "format": "date-time"
          }
        },
        "additionalProperties": false
      },
      "Supplier.PurchaseAllocation": {
        "type": "object",
        "properties": {
          "SalesOrderItem": {
            "$ref": "#/components/schemas/Order.OrderItemIdentifier"
          },
          "WorkOrderItem": {
            "$ref": "#/components/schemas/Order.OrderItemIdentifier"
          },
          "Quantity": {
            "type": "number",
            "format": "double"
          },
          "Received": {
            "type": "number",
            "format": "double"
          },
          "Notes": {
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Supplier.PurchaseOrder": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid"
          },
          "OrderId": {
            "type": "string",
            "format": "uuid"
          },
          "Number": {
            "type": "string",
            "nullable": true
          },
          "SupplierChannel": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "SupplierNumber": {
            "type": "string",
            "nullable": true
          },
          "SendToSupplier": {
            "type": "boolean",
            "nullable": true
          },
          "PurchaseOrderType": {
            "$ref": "#/components/schemas/Supplier.PurchaseOrderType"
          },
          "OrderDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "Currency": {
            "type": "string",
            "nullable": true
          },
          "ReceiveLocationId": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "ReceiveLocation": {
            "type": "string",
            "nullable": true
          },
          "Status": {
            "type": "string",
            "nullable": true
          },
          "SupplierStatus": {
            "type": "string",
            "nullable": true
          },
          "ShippingServiceLevel": {
            "type": "string",
            "nullable": true
          },
          "RequestedServiceLevel": {
            "type": "string",
            "nullable": true
          },
          "ShippingMethod": {
            "type": "string",
            "nullable": true
          },
          "BillTo": {
            "$ref": "#/components/schemas/Contact.Contact"
          },
          "ShipTo": {
            "$ref": "#/components/schemas/Contact.Contact"
          },
          "Items": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Supplier.PurchaseOrderItem"
            },
            "nullable": true
          },
          "Options": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Order.OrderOption"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Supplier.PurchaseOrderCommitment": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid"
          },
          "Sku": {
            "type": "string",
            "nullable": true
          },
          "Quantity": {
            "type": "number",
            "format": "double"
          },
          "Notes": {
            "type": "string",
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Supplier.PurchaseOrderItem": {
        "type": "object",
        "properties": {
          "Id": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "AutoCreate": {
            "type": "boolean",
            "nullable": true
          },
          "LineNum": {
            "type": "integer",
            "format": "int32"
          },
          "MasterSku": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "ChannelSku": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "Sku": {
            "type": "string",
            "nullable": true
          },
          "PartNo": {
            "type": "string",
            "nullable": true
          },
          "UomCode": {
            "type": "string",
            "nullable": true
          },
          "UomQuantity": {
            "type": "number",
            "format": "double"
          },
          "UnitCost": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "UnitDiscount": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "ExtendedCost": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Ordered": {
            "type": "number",
            "format": "double"
          },
          "PurchaseLocation": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "Received": {
            "type": "number",
            "format": "double"
          },
          "ReceiveLocation": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "Commitments": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Supplier.PurchaseOrderCommitment"
            },
            "nullable": true
          },
          "PurchaseAllocations": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Supplier.PurchaseAllocation"
            },
            "nullable": true
          },
          "Receipts": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Supplier.ItemReceipt"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Supplier.PurchaseOrderSearch": {
        "type": "object",
        "properties": {
          "SupplierChannel": {
            "$ref": "#/components/schemas/Base.Identifier"
          },
          "PurchaseOrderType": {
            "$ref": "#/components/schemas/Supplier.PurchaseOrderType"
          },
          "Status": {
            "type": "string",
            "nullable": true
          },
          "OrderDate": {
            "$ref": "#/components/schemas/Base.DateRange"
          },
          "ModifiedDate": {
            "$ref": "#/components/schemas/Base.DateRange"
          },
          "PageSize": {
            "type": "integer",
            "format": "int32"
          },
          "Background": {
            "type": "boolean"
          },
          "OrderModified": {
            "type": "boolean"
          },
          "UseModifiedSearch": {
            "type": "boolean",
            "readOnly": true
          },
          "HasValue": {
            "type": "boolean",
            "readOnly": true
          }
        },
        "additionalProperties": false
      },
      "Supplier.PurchaseOrderType": {
        "enum": [
          "Warehouse",
          "Dropship",
          "Fulfillment",
          "Transfer",
          "Return"
        ],
        "type": "string"
      },
      "Supplier.PurchaseReceipt": {
        "type": "object",
        "properties": {
          "PurchaseOrderId": {
            "type": "string",
            "format": "uuid"
          },
          "ReceiptDate": {
            "type": "string",
            "format": "date-time",
            "nullable": true
          },
          "ReceiveLocation": {
            "type": "string",
            "format": "uuid",
            "nullable": true
          },
          "Complete": {
            "type": "boolean"
          },
          "Items": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Supplier.PurchaseReceiptItem"
            },
            "nullable": true
          }
        },
        "additionalProperties": false
      },
      "Supplier.PurchaseReceiptItem": {
        "type": "object",
        "properties": {
          "LineNum": {
            "type": "integer",
            "format": "int32"
          },
          "Received": {
            "type": "integer",
            "format": "int32"
          },
          "BaseUnits": {
            "type": "boolean"
          }
        },
        "additionalProperties": false
      },
      "Units.DimensionType": {
        "type": "object",
        "properties": {
          "Unit": {
            "$ref": "#/components/schemas/Units.DimensionUnitType"
          },
          "Length": {
            "type": "number",
            "format": "double"
          },
          "Width": {
            "type": "number",
            "format": "double"
          },
          "Height": {
            "type": "number",
            "format": "double"
          },
          "Empty": {
            "type": "boolean",
            "readOnly": true
          },
          "Volume": {
            "type": "number",
            "format": "double",
            "readOnly": true
          },
          "Girth": {
            "type": "number",
            "format": "double",
            "readOnly": true
          },
          "GirthLength": {
            "type": "number",
            "format": "double",
            "readOnly": true
          },
          "LongestDimension": {
            "type": "number",
            "format": "double",
            "readOnly": true
          },
          "ShortestDimension": {
            "type": "number",
            "format": "double",
            "readOnly": true
          },
          "MedianDimension": {
            "type": "number",
            "format": "double",
            "readOnly": true
          }
        },
        "additionalProperties": false
      },
      "Units.DimensionUnitType": {
        "enum": [
          "Inch",
          "Foot",
          "Meter",
          "Centimeter",
          "Millimeter",
          "NotSpecified"
        ],
        "type": "string"
      },
      "Units.PageSize": {
        "type": "object",
        "properties": {
          "DimensionUnit": {
            "$ref": "#/components/schemas/Units.DimensionUnitType"
          },
          "Width": {
            "type": "number",
            "format": "double"
          },
          "Height": {
            "type": "number",
            "format": "double"
          }
        },
        "additionalProperties": false
      },
      "Units.WeightType": {
        "type": "object",
        "properties": {
          "Unit": {
            "$ref": "#/components/schemas/Units.WeightUnitType"
          },
          "Value": {
            "type": "number",
            "format": "double"
          },
          "DimensionalWeight": {
            "type": "number",
            "format": "double",
            "nullable": true
          },
          "Dimensions": {
            "$ref": "#/components/schemas/Units.DimensionType"
          }
        },
        "additionalProperties": false
      },
      "Units.WeightUnitType": {
        "enum": [
          "Pound",
          "Ounce",
          "Gram",
          "Milligram",
          "Kilogram",
          "NotSpecified"
        ],
        "type": "string"
      }
    },
    "securitySchemes": {
      "ApiKey": {
        "type": "apiKey",
        "description": "EVP Authentication Token",
        "name": "x-evp-authentication",
        "in": "header"
      }
    }
  }
}
