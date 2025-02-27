![photo_2025-02-27_19-52-24](https://github.com/user-attachments/assets/53f801d6-14db-4f63-8361-11058a501ba3)
[Grafana server dashboard.json](https://github.com/user-attachments/files/19012304/Grafana.server.dashboard.json)

{
  "annotations": {
    "list": [
      {
        "builtIn": 1,
        "datasource": {
          "type": "grafana",
          "uid": "-- Grafana --"
        },
        "enable": true,
        "hide": true,
        "iconColor": "rgba(0, 211, 255, 1)",
        "name": "Annotations & Alerts",
        "type": "dashboard"
      }
    ]
  },
  "description": "Dashboard with information about my server and pc",
  "editable": true,
  "fiscalYearStartMonth": 0,
  "graphTooltip": 0,
  "id": 1,
  "links": [],
  "panels": [
    {
      "collapsed": false,
      "gridPos": {
        "h": 1,
        "w": 24,
        "x": 0,
        "y": 0
      },
      "id": 13,
      "panels": [],
      "title": "Row title",
      "type": "row"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "decimals": 1,
          "mappings": [],
          "max": 100,
          "min": 0,
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "#00b4d8",
                "value": null
              },
              {
                "color": "#ff5252",
                "value": 80
              }
            ]
          },
          "unit": "percent"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 5,
        "w": 3,
        "x": 0,
        "y": 1
      },
      "id": 3,
      "options": {
        "minVizHeight": 75,
        "minVizWidth": 75,
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showThresholdLabels": false,
        "showThresholdMarkers": false,
        "sizing": "auto"
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "code",
          "exemplar": false,
          "expr": "avg without (mode,cpu) (\r\n  100 * (1 - rate(node_cpu_seconds_total{mode=\"idle\"}[1m]))\r\n)",
          "fullMetaSearch": false,
          "includeNullMetadata": true,
          "instant": true,
          "legendFormat": "",
          "range": false,
          "refId": "A",
          "useBackend": false
        }
      ],
      "title": "CPU usage",
      "type": "gauge"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "decimals": 1,
          "mappings": [],
          "max": 100,
          "min": 0,
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "#00b4d8",
                "value": null
              },
              {
                "color": "#ff5252",
                "value": 80
              }
            ]
          },
          "unit": "percent"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 5,
        "w": 3,
        "x": 3,
        "y": 1
      },
      "id": 4,
      "options": {
        "minVizHeight": 75,
        "minVizWidth": 75,
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showThresholdLabels": false,
        "showThresholdMarkers": false,
        "sizing": "auto"
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "editorMode": "code",
          "expr": "100 * (1 - ((avg_over_time(node_memory_MemFree_bytes[10m]) + avg_over_time(node_memory_Cached_bytes[10m]) + avg_over_time(node_memory_Buffers_bytes[10m])) / avg_over_time(node_memory_MemTotal_bytes[10m])))",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "Ram Usage",
      "type": "gauge"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "description": "",
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "#ff4500",
            "mode": "shades"
          },
          "displayName": "Upload",
          "fieldMinMax": false,
          "mappings": [
            {
              "options": {
                "{__name__=\"speedtest_upload\", instance=\"127.0.0.1:9100\", job=\"node_exporter_metrics\"}": {
                  "index": 0,
                  "text": "nigga"
                }
              },
              "type": "value"
            }
          ],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "dark-red",
                "value": 100
              },
              {
                "color": "#f94710",
                "value": 200
              }
            ]
          },
          "unit": "bps"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 3,
        "w": 4,
        "x": 6,
        "y": 1
      },
      "id": 30,
      "options": {
        "colorMode": "background",
        "graphMode": "area",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "builder",
          "expr": "speedtest_upload{instance=\"127.0.0.1:9100\"}",
          "fullMetaSearch": false,
          "includeNullMetadata": true,
          "interval": "",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A",
          "useBackend": false
        }
      ],
      "title": "",
      "type": "stat"
    },
    {
      "datasource": {
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "fieldMinMax": false,
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "#8a2be2",
                "value": null
              },
              {
                "color": "dark-red",
                "value": 52596
              }
            ]
          },
          "unit": "h"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 14,
        "w": 2,
        "x": 10,
        "y": 1
      },
      "id": 25,
      "options": {
        "colorMode": "background",
        "graphMode": "none",
        "justifyMode": "center",
        "orientation": "horizontal",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "auto",
        "wideLayout": true
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "builder",
          "exemplar": false,
          "expr": "smartmon_power_on_hours_raw_value{disk=\"/dev/sda\"}",
          "format": "time_series",
          "fullMetaSearch": false,
          "includeNullMetadata": true,
          "instant": false,
          "legendFormat": "/dev/sda",
          "range": true,
          "refId": "A",
          "useBackend": false
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "disableTextWrap": false,
          "editorMode": "builder",
          "expr": "smartmon_power_on_hours_raw_value{disk=\"/dev/sdb\"}",
          "fullMetaSearch": false,
          "hide": false,
          "includeNullMetadata": true,
          "legendFormat": "/dev/sdb",
          "range": true,
          "refId": "B",
          "useBackend": false
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "disableTextWrap": false,
          "editorMode": "builder",
          "expr": "smartmon_power_on_hours_raw_value{disk=\"/dev/sdc\"}",
          "fullMetaSearch": false,
          "hide": false,
          "includeNullMetadata": true,
          "legendFormat": "/dev/sdc",
          "range": true,
          "refId": "C",
          "useBackend": false
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "disableTextWrap": false,
          "editorMode": "builder",
          "expr": "smartmon_power_on_hours_raw_value{disk=\"/dev/sdd\"}",
          "fullMetaSearch": false,
          "hide": false,
          "includeNullMetadata": true,
          "legendFormat": "/dev/sdd",
          "range": true,
          "refId": "D",
          "useBackend": false
        }
      ],
      "title": "",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "#b027d8",
            "mode": "shades"
          },
          "custom": {
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            }
          },
          "fieldMinMax": false,
          "mappings": [],
          "unit": "bytes"
        },
        "overrides": [
          {
            "matcher": {
              "id": "byName",
              "options": "Free space"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "#e0d7ff",
                  "mode": "shades"
                }
              }
            ]
          }
        ]
      },
      "gridPos": {
        "h": 8,
        "w": 3,
        "x": 12,
        "y": 1
      },
      "id": 33,
      "options": {
        "displayLabels": [],
        "legend": {
          "displayMode": "table",
          "placement": "bottom",
          "showLegend": true,
          "values": [
            "value"
          ]
        },
        "pieType": "donut",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "tooltip": {
          "hideZeros": false,
          "mode": "single",
          "sort": "desc"
        }
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "editorMode": "code",
          "expr": "node_filesystem_avail_bytes{device=\"/dev/sda1\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/mnt/Immichi_Storage-1\"}",
          "legendFormat": "Free space",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "editorMode": "code",
          "expr": "node_filesystem_size_bytes{device=\"/dev/sda1\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/mnt/Immichi_Storage-1\"} - node_filesystem_avail_bytes{device=\"/dev/sda1\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/mnt/Immichi_Storage-1\"}",
          "hide": false,
          "instant": false,
          "legendFormat": "Used space",
          "range": true,
          "refId": "B"
        }
      ],
      "title": "sda free space",
      "type": "piechart"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "#b027d8",
            "mode": "shades"
          },
          "custom": {
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            }
          },
          "fieldMinMax": false,
          "mappings": [],
          "unit": "bytes"
        },
        "overrides": [
          {
            "matcher": {
              "id": "byName",
              "options": "Free space"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "#e0d7ff",
                  "mode": "shades"
                }
              }
            ]
          }
        ]
      },
      "gridPos": {
        "h": 8,
        "w": 3,
        "x": 15,
        "y": 1
      },
      "id": 34,
      "options": {
        "displayLabels": [],
        "legend": {
          "displayMode": "table",
          "placement": "bottom",
          "showLegend": true,
          "values": [
            "value"
          ]
        },
        "pieType": "donut",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "tooltip": {
          "hideZeros": false,
          "mode": "single",
          "sort": "desc"
        }
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "code",
          "expr": "node_filesystem_avail_bytes{device=\"/dev/sdb1\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/mnt/Storage1_sdb1-/dev/sdb1\"}",
          "fullMetaSearch": false,
          "includeNullMetadata": true,
          "legendFormat": "Free space",
          "range": true,
          "refId": "A",
          "useBackend": false
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "editorMode": "code",
          "expr": "node_filesystem_size_bytes{device=\"/dev/sdb1\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/mnt/Storage1_sdb1-/dev/sdb1\"} - node_filesystem_avail_bytes{device=\"/dev/sdb1\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/mnt/Storage1_sdb1-/dev/sdb1\"}",
          "hide": false,
          "instant": false,
          "legendFormat": "Used space",
          "range": true,
          "refId": "B"
        }
      ],
      "title": "sdb free space",
      "type": "piechart"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "#b027d8",
            "mode": "shades"
          },
          "custom": {
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            }
          },
          "fieldMinMax": false,
          "mappings": [],
          "unit": "bytes"
        },
        "overrides": [
          {
            "matcher": {
              "id": "byName",
              "options": "Free space"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "#e0d7ff",
                  "mode": "shades"
                }
              }
            ]
          }
        ]
      },
      "gridPos": {
        "h": 8,
        "w": 3,
        "x": 18,
        "y": 1
      },
      "id": 35,
      "options": {
        "displayLabels": [],
        "legend": {
          "displayMode": "table",
          "placement": "bottom",
          "showLegend": true,
          "values": [
            "value"
          ]
        },
        "pieType": "donut",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "tooltip": {
          "hideZeros": false,
          "mode": "single",
          "sort": "desc"
        }
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "editorMode": "code",
          "expr": "node_filesystem_avail_bytes{device=\"/dev/mapper/ubuntu--vg--1-ubuntu--lv\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/\"}",
          "legendFormat": "Free space",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "editorMode": "code",
          "expr": "node_filesystem_size_bytes{device=\"/dev/mapper/ubuntu--vg--1-ubuntu--lv\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/\"} - node_filesystem_avail_bytes{device=\"/dev/mapper/ubuntu--vg--1-ubuntu--lv\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/\"}",
          "hide": false,
          "instant": false,
          "legendFormat": "Used space",
          "range": true,
          "refId": "B"
        }
      ],
      "title": "sdc free space",
      "type": "piechart"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "#b027d8",
            "mode": "shades"
          },
          "custom": {
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            }
          },
          "fieldMinMax": false,
          "mappings": [],
          "unit": "bytes"
        },
        "overrides": [
          {
            "matcher": {
              "id": "byName",
              "options": "Free space"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "#e0d7ff",
                  "mode": "shades"
                }
              }
            ]
          }
        ]
      },
      "gridPos": {
        "h": 8,
        "w": 3,
        "x": 21,
        "y": 1
      },
      "id": 36,
      "options": {
        "displayLabels": [],
        "legend": {
          "displayMode": "table",
          "placement": "bottom",
          "showLegend": true,
          "sortBy": "Value",
          "sortDesc": false,
          "values": [
            "value"
          ]
        },
        "pieType": "donut",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "tooltip": {
          "hideZeros": false,
          "mode": "single",
          "sort": "desc"
        }
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "editorMode": "code",
          "expr": "node_filesystem_avail_bytes{device=\"/dev/sdd1\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/mnt/MovieDrive\"} ",
          "legendFormat": "Free space",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "editorMode": "code",
          "expr": "node_filesystem_size_bytes{device=\"/dev/sdd1\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/mnt/MovieDrive\"}  - node_filesystem_avail_bytes{device=\"/dev/sdd1\",device_error=\"\",fstype=\"ext4\",mountpoint=\"/mnt/MovieDrive\"} ",
          "hide": false,
          "instant": false,
          "legendFormat": "Used space",
          "range": true,
          "refId": "B"
        }
      ],
      "title": "sdd free space",
      "type": "piechart"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "#ff4500",
            "mode": "shades"
          },
          "displayName": "Download",
          "fieldMinMax": false,
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 100
              },
              {
                "color": "green",
                "value": 200
              }
            ]
          },
          "unit": "bps"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 3,
        "w": 4,
        "x": 6,
        "y": 4
      },
      "id": 31,
      "options": {
        "colorMode": "background",
        "graphMode": "area",
        "justifyMode": "auto",
        "orientation": "horizontal",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "builder",
          "expr": "speedtest_download{instance=\"127.0.0.1:9100\"}",
          "fullMetaSearch": false,
          "includeNullMetadata": true,
          "legendFormat": "__auto",
          "range": true,
          "refId": "A",
          "useBackend": false
        }
      ],
      "title": "",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "max": 70,
          "min": 0,
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "#00b4d8",
                "value": null
              },
              {
                "color": "dark-red",
                "value": 55
              }
            ]
          },
          "unit": "celsius"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 9,
        "w": 6,
        "x": 0,
        "y": 6
      },
      "id": 21,
      "options": {
        "displayMode": "gradient",
        "legend": {
          "calcs": [],
          "displayMode": "list",
          "placement": "bottom",
          "showLegend": false
        },
        "maxVizHeight": 300,
        "minVizHeight": 16,
        "minVizWidth": 8,
        "namePlacement": "left",
        "orientation": "horizontal",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showUnfilled": true,
        "sizing": "auto",
        "valueMode": "color"
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "editorMode": "code",
          "expr": "node_hwmon_temp_celsius{chip=\"platform_coretemp_0\",sensor=\"temp5\"}",
          "instant": false,
          "interval": "",
          "legendFormat": "CPU",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "editorMode": "code",
          "expr": "node_hwmon_temp_celsius{chip=\"0000:00:01_0_0000:01:00_0\",sensor=\"temp1\"}",
          "hide": false,
          "instant": false,
          "legendFormat": "GPU",
          "range": true,
          "refId": "B"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "editorMode": "code",
          "expr": "smartmon_temperature_celsius_raw_value{disk=\"/dev/sda\",smart_id=\"194\",type=\"sat\"}",
          "hide": false,
          "instant": false,
          "legendFormat": "SDA",
          "range": true,
          "refId": "C"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "editorMode": "code",
          "expr": "smartmon_temperature_celsius_raw_value{disk=\"/dev/sdb\",smart_id=\"194\",type=\"sat\"}",
          "hide": false,
          "instant": false,
          "interval": "",
          "legendFormat": "SDB",
          "range": true,
          "refId": "D"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "editorMode": "code",
          "expr": "smartmon_temperature_celsius_raw_value{disk=\"/dev/sdc\",smart_id=\"194\",type=\"sat\"}",
          "hide": false,
          "instant": false,
          "legendFormat": "SDC",
          "range": true,
          "refId": "E"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "editorMode": "code",
          "exemplar": false,
          "expr": "smartmon_temperature_celsius_raw_value{disk=\"/dev/sdd\",smart_id=\"194\",type=\"sat\"}",
          "hide": false,
          "instant": false,
          "legendFormat": "SDD",
          "range": true,
          "refId": "F"
        }
      ],
      "title": "Temperatures",
      "type": "bargauge"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "#ff4500",
            "mode": "shades"
          },
          "displayName": "Ping",
          "fieldMinMax": false,
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 100
              }
            ]
          },
          "unit": "ms"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 3,
        "w": 4,
        "x": 6,
        "y": 7
      },
      "id": 32,
      "options": {
        "colorMode": "background",
        "graphMode": "area",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "builder",
          "expr": "speedtest_ping{instance=\"127.0.0.1:9100\"}",
          "fullMetaSearch": false,
          "includeNullMetadata": true,
          "legendFormat": "__auto",
          "range": true,
          "refId": "A",
          "useBackend": false
        }
      ],
      "title": "",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "prometheus"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "custom": {
            "align": "auto",
            "cellOptions": {
              "type": "auto"
            },
            "filterable": true,
            "inspect": false
          },
          "decimals": 2,
          "displayName": "",
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 6,
        "w": 12,
        "x": 12,
        "y": 9
      },
      "id": 29,
      "options": {
        "cellHeight": "sm",
        "footer": {
          "countRows": false,
          "fields": "",
          "reducer": [
            "sum"
          ],
          "show": false
        },
        "showHeader": true
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "prometheus"
          },
          "editorMode": "code",
          "expr": "smartmon_device_info",
          "format": "table",
          "instant": true,
          "interval": "",
          "intervalFactor": 1,
          "refId": "A"
        }
      ],
      "title": "Device_Info",
      "transformations": [
        {
          "id": "filterFieldsByName",
          "options": {
            "include": {
              "names": [
                "disk",
                "firmware_version",
                "instance",
                "model_family",
                "model_name",
                "serial_number",
                "type"
              ]
            }
          }
        },
        {
          "id": "organize",
          "options": {
            "excludeByName": {},
            "includeByName": {},
            "indexByName": {
              "Value": 7,
              "disk": 1,
              "firmware_version": 5,
              "instance": 0,
              "model_family": 4,
              "model_name": 3,
              "serial_number": 6,
              "type": 2
            },
            "renameByName": {}
          }
        },
        {
          "id": "sortBy",
          "options": {
            "fields": {},
            "sort": [
              {
                "field": "instance"
              }
            ]
          }
        }
      ],
      "type": "table"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "displayName": "Uptime",
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "#007bff",
                "value": null
              }
            ]
          },
          "unit": "s"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 5,
        "w": 4,
        "x": 6,
        "y": 10
      },
      "id": 2,
      "options": {
        "colorMode": "background",
        "graphMode": "none",
        "justifyMode": "center",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "beav41hdt59fkf"
          },
          "disableTextWrap": false,
          "editorMode": "code",
          "expr": "node_time_seconds - node_boot_time_seconds",
          "fullMetaSearch": false,
          "hide": false,
          "includeNullMetadata": true,
          "instant": false,
          "legendFormat": "__auto",
          "range": true,
          "refId": "A",
          "useBackend": false
        }
      ],
      "title": "",
      "type": "stat"
    },
    {
      "collapsed": false,
      "gridPos": {
        "h": 1,
        "w": 24,
        "x": 0,
        "y": 15
      },
      "id": 14,
      "panels": [],
      "title": "Up Status",
      "type": "row"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "light-green",
            "mode": "shades"
          },
          "displayName": "Arduino Temp",
          "mappings": [
            {
              "options": {
                "0": {
                  "color": "#8e0414",
                  "index": 1,
                  "text": "Down"
                },
                "1": {
                  "color": "#0b2155",
                  "index": 0,
                  "text": "UP"
                }
              },
              "type": "value"
            }
          ],
          "noValue": "Down",
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          }
        },
        "overrides": [
          {
            "__systemRef": "hideSeriesFrom",
            "matcher": {
              "id": "byNames",
              "options": {
                "mode": "exclude",
                "names": [
                  "{__name__=\"probe_success\", instance=\"http://127.0.0.1:2283\", job=\"blackbox\"}"
                ],
                "prefix": "All except:",
                "readOnly": true
              }
            },
            "properties": []
          }
        ]
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 0,
        "y": 16
      },
      "id": 24,
      "options": {
        "colorMode": "background",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "builder",
          "expr": "{__name__=\"probe_success\", instance=\"http://192.168.11.83\", job=\"blackbox\"}",
          "fullMetaSearch": false,
          "includeNullMetadata": true,
          "legendFormat": "__auto",
          "range": true,
          "refId": "A",
          "useBackend": false
        }
      ],
      "title": "",
      "transparent": true,
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "light-green",
            "mode": "shades"
          },
          "displayName": "CasaOs",
          "mappings": [
            {
              "options": {
                "0": {
                  "color": "#8e0414",
                  "index": 1,
                  "text": "Down"
                },
                "1": {
                  "color": "#0b2155",
                  "index": 0,
                  "text": "UP"
                }
              },
              "type": "value"
            }
          ],
          "noValue": "Down",
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          }
        },
        "overrides": [
          {
            "__systemRef": "hideSeriesFrom",
            "matcher": {
              "id": "byNames",
              "options": {
                "mode": "exclude",
                "names": [
                  "{__name__=\"probe_success\", instance=\"http://127.0.0.1:2283\", job=\"blackbox\"}"
                ],
                "prefix": "All except:",
                "readOnly": true
              }
            },
            "properties": []
          }
        ]
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 3,
        "y": 16
      },
      "id": 20,
      "options": {
        "colorMode": "background",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "editorMode": "code",
          "expr": "{__name__=\"probe_success\", instance=\"http://127.0.0.1:80\", job=\"blackbox\"}",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "",
      "transparent": true,
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "light-green",
            "mode": "shades"
          },
          "displayName": "Tailscale",
          "mappings": [
            {
              "options": {
                "0": {
                  "color": "#8e0414",
                  "index": 1,
                  "text": "Down"
                },
                "1": {
                  "color": "#0b2155",
                  "index": 0,
                  "text": "UP"
                }
              },
              "type": "value"
            }
          ],
          "noValue": "Down",
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          }
        },
        "overrides": [
          {
            "__systemRef": "hideSeriesFrom",
            "matcher": {
              "id": "byNames",
              "options": {
                "mode": "exclude",
                "names": [
                  "{__name__=\"probe_success\", instance=\"http://127.0.0.1:2283\", job=\"blackbox\"}"
                ],
                "prefix": "All except:",
                "readOnly": true
              }
            },
            "properties": []
          }
        ]
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 6,
        "y": 16
      },
      "id": 18,
      "options": {
        "colorMode": "background",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "editorMode": "code",
          "expr": "{__name__=\"probe_success\", instance=\"http://100.65.198.41\", job=\"blackbox\"}",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "",
      "transparent": true,
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "light-green",
            "mode": "shades"
          },
          "displayName": "Qbittorrent",
          "mappings": [
            {
              "options": {
                "0": {
                  "color": "#8e0414",
                  "index": 1,
                  "text": "Down"
                },
                "1": {
                  "color": "#0b2155",
                  "index": 0,
                  "text": "UP"
                }
              },
              "type": "value"
            }
          ],
          "noValue": "Down",
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          }
        },
        "overrides": [
          {
            "__systemRef": "hideSeriesFrom",
            "matcher": {
              "id": "byNames",
              "options": {
                "mode": "exclude",
                "names": [
                  "{__name__=\"probe_success\", instance=\"http://127.0.0.1:2283\", job=\"blackbox\"}"
                ],
                "prefix": "All except:",
                "readOnly": true
              }
            },
            "properties": []
          }
        ]
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 9,
        "y": 16
      },
      "id": 19,
      "options": {
        "colorMode": "background",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "editorMode": "code",
          "expr": "{__name__=\"probe_success\", instance=\"http://127.0.0.1:8080\", job=\"blackbox\"}",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "",
      "transparent": true,
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "light-green",
            "mode": "shades"
          },
          "displayName": "Emby",
          "mappings": [
            {
              "options": {
                "0": {
                  "color": "#8e0414",
                  "index": 1,
                  "text": "Down"
                },
                "1": {
                  "color": "#0b2155",
                  "index": 0,
                  "text": "UP"
                }
              },
              "type": "value"
            }
          ],
          "noValue": "Down",
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          }
        },
        "overrides": [
          {
            "__systemRef": "hideSeriesFrom",
            "matcher": {
              "id": "byNames",
              "options": {
                "mode": "exclude",
                "names": [
                  "{__name__=\"probe_success\", instance=\"http://127.0.0.1:2283\", job=\"blackbox\"}"
                ],
                "prefix": "All except:",
                "readOnly": true
              }
            },
            "properties": []
          }
        ]
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 12,
        "y": 16
      },
      "id": 22,
      "options": {
        "colorMode": "background",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "editorMode": "code",
          "expr": "{__name__=\"probe_success\", instance=\"http://127.0.0.1:8097\", job=\"blackbox\"}",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "",
      "transparent": true,
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "light-green",
            "mode": "shades"
          },
          "displayName": "Immichi",
          "mappings": [
            {
              "options": {
                "0": {
                  "color": "#8e0414",
                  "index": 1,
                  "text": "Down"
                },
                "1": {
                  "color": "#0b2155",
                  "index": 0,
                  "text": "UP"
                }
              },
              "type": "value"
            }
          ],
          "noValue": "Down",
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          }
        },
        "overrides": [
          {
            "__systemRef": "hideSeriesFrom",
            "matcher": {
              "id": "byNames",
              "options": {
                "mode": "exclude",
                "names": [
                  "{__name__=\"probe_success\", instance=\"http://127.0.0.1:2283\", job=\"blackbox\"}"
                ],
                "prefix": "All except:",
                "readOnly": true
              }
            },
            "properties": []
          }
        ]
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 15,
        "y": 16
      },
      "id": 9,
      "options": {
        "colorMode": "background",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "editorMode": "code",
          "expr": "{__name__=\"probe_success\", instance=\"http://127.0.0.1:2283\", job=\"blackbox\"}",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "",
      "transparent": true,
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "light-green",
            "mode": "shades"
          },
          "displayName": "Home Assistant",
          "mappings": [
            {
              "options": {
                "0": {
                  "color": "#8e0414",
                  "index": 1,
                  "text": "Down"
                },
                "1": {
                  "color": "#0b2155",
                  "index": 0,
                  "text": "UP"
                }
              },
              "type": "value"
            }
          ],
          "noValue": "Down",
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          }
        },
        "overrides": [
          {
            "__systemRef": "hideSeriesFrom",
            "matcher": {
              "id": "byNames",
              "options": {
                "mode": "exclude",
                "names": [
                  "{__name__=\"probe_success\", instance=\"http://127.0.0.1:2283\", job=\"blackbox\"}"
                ],
                "prefix": "All except:",
                "readOnly": true
              }
            },
            "properties": []
          }
        ]
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 18,
        "y": 16
      },
      "id": 15,
      "options": {
        "colorMode": "background",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "editorMode": "code",
          "expr": "{__name__=\"probe_success\", instance=\"http://127.0.0.1:8123\", job=\"blackbox\"}",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "",
      "transparent": true,
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "beav41hdt59fkf"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "light-green",
            "mode": "shades"
          },
          "displayName": "Next Cloud",
          "mappings": [
            {
              "options": {
                "0": {
                  "color": "#8e0414",
                  "index": 1,
                  "text": "Down"
                },
                "1": {
                  "color": "#0b2155",
                  "index": 0,
                  "text": "UP"
                }
              },
              "type": "value"
            }
          ],
          "noValue": "Down",
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          }
        },
        "overrides": [
          {
            "__systemRef": "hideSeriesFrom",
            "matcher": {
              "id": "byNames",
              "options": {
                "mode": "exclude",
                "names": [
                  "{__name__=\"probe_success\", instance=\"http://127.0.0.1:2283\", job=\"blackbox\"}"
                ],
                "prefix": "All except:",
                "readOnly": true
              }
            },
            "properties": []
          }
        ]
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 21,
        "y": 16
      },
      "id": 17,
      "options": {
        "colorMode": "background",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "value_and_name",
        "wideLayout": false
      },
      "pluginVersion": "11.5.2",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "builder",
          "expr": "{__name__=\"probe_success\", instance=\"http://127.0.0.1:10081\", job=\"blackbox\"}",
          "fullMetaSearch": false,
          "includeNullMetadata": true,
          "legendFormat": "__auto",
          "range": true,
          "refId": "A",
          "useBackend": false
        }
      ],
      "title": "",
      "transparent": true,
      "type": "stat"
    }
  ],
  "preload": false,
  "refresh": "10s",
  "schemaVersion": 40,
  "tags": [],
  "templating": {
    "list": []
  },
  "time": {
    "from": "now-5m",
    "to": "now"
  },
  "timepicker": {},
  "timezone": "browser",
  "title": "Main Dashboard",
  "uid": "ceav3t54hje9sd",
  "version": 42,
  "weekStart": ""
}
