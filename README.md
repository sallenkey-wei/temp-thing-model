{
  "schema": "https://iotx-tsl.oss-ap-southeast-1.aliyuncs.com/schema.json",
  "profile": {
    "productKey": "a1lWJ8PP4mu"
  },
  "services": [
    {
      "outputData": [],
      "identifier": "set",
      "inputData": [],
      "method": "thing.service.property.set",
      "name": "set",
      "required": true,
      "callType": "async",
      "desc": "属性设置"
    },
    {
      "outputData": [
        {
          "identifier": "LockState",
          "dataType": {
            "specs": {
              "0": "关闭",
              "1": "打开"
            },
            "type": "enum"
          },
          "name": "门锁状态"
        }
      ],
      "identifier": "get",
      "inputData": [
        "LockState"
      ],
      "method": "thing.service.property.get",
      "name": "get",
      "required": true,
      "callType": "async",
      "desc": "属性获取"
    },
    {
      "outputData": [],
      "identifier": "AddKey",
      "inputData": [
        {
          "identifier": "LockType",
          "dataType": {
            "specs": {
              "1": "指纹",
              "2": "密码",
              "3": "卡",
              "4": "机械钥匙"
            },
            "type": "enum"
          },
          "name": "开锁方式"
        },
        {
          "identifier": "UserLimit",
          "dataType": {
            "specs": {
              "1": "普通用户",
              "2": "管理员",
              "3": "劫持用户"
            },
            "type": "enum"
          },
          "name": "用户权限"
        }
      ],
      "method": "thing.service.AddKey",
      "name": "添加钥匙",
      "required": true,
      "callType": "async"
    },
    {
      "outputData": [],
      "identifier": "DeleteKey",
      "inputData": [
        {
          "identifier": "KeyID",
          "dataType": {
            "specs": {
              "length": "10"
            },
            "type": "text"
          },
          "name": "钥匙ID"
        },
        {
          "identifier": "LockType",
          "dataType": {
            "specs": {
              "1": "指纹",
              "2": "密码",
              "3": "卡",
              "4": "机械钥匙"
            },
            "type": "enum"
          },
          "name": "开锁方式"
        }
      ],
      "method": "thing.service.DeleteKey",
      "name": "删除钥匙",
      "required": true,
      "callType": "async"
    },
    {
      "outputData": [
        {
          "identifier": "KeyID",
          "dataType": {
            "specs": {
              "length": "10"
            },
            "type": "text"
          },
          "name": "钥匙ID"
        },
        {
          "identifier": "LockType",
          "dataType": {
            "specs": {
              "1": "指纹",
              "2": "密码",
              "3": "卡",
              "4": "机械钥匙"
            },
            "type": "enum"
          },
          "name": "开锁方式"
        },
        {
          "identifier": "UserLimit",
          "dataType": {
            "specs": {
              "1": "普通用户",
              "2": "管理员",
              "3": "劫持用户"
            },
            "type": "enum"
          },
          "name": "用户权限"
        },
        {
          "identifier": "IsValid",
          "dataType": {
            "specs": {
              "0": "无效",
              "1": "有效"
            },
            "type": "bool"
          },
          "name": "是否有效"
        },
        {
          "identifier": "KeyNickName",
          "dataType": {
            "specs": {
              "length": "255"
            },
            "type": "text"
          },
          "name": "钥匙昵称"
        }
      ],
      "identifier": "GetKeyList",
      "inputData": [
        {
          "identifier": "LockType",
          "dataType": {
            "specs": {
              "0": "全部",
              "1": "指纹",
              "2": "密码",
              "3": "卡",
              "4": "机械钥匙"
            },
            "type": "enum"
          },
          "name": "开锁方式"
        }
      ],
      "method": "thing.service.GetKeyList",
      "name": "获取钥匙列表",
      "required": true,
      "callType": "async"
    }
  ],
  "properties": [
    {
      "identifier": "LockState",
      "dataType": {
        "specs": {
          "0": "关闭",
          "1": "打开"
        },
        "type": "enum"
      },
      "name": "门锁状态",
      "accessMode": "r",
      "required": true
    }
  ],
  "events": [
    {
      "outputData": [
        {
          "identifier": "LockState",
          "dataType": {
            "specs": {
              "0": "关闭",
              "1": "打开"
            },
            "type": "enum"
          },
          "name": "门锁状态"
        }
      ],
      "identifier": "post",
      "method": "thing.event.property.post",
      "name": "post",
      "type": "info",
      "required": true,
      "desc": "属性上报"
    },
    {
      "outputData": [
        {
          "identifier": "ErrorCode",
          "dataType": {
            "specs": {
              "0": "正常"
            },
            "type": "enum"
          },
          "name": "故障代码"
        }
      ],
      "identifier": "Error",
      "method": "thing.event.Error.post",
      "name": "故障上报",
      "type": "info",
      "required": true
    },
    {
      "outputData": [
        {
          "identifier": "KeyID",
          "dataType": {
            "specs": {
              "length": "10"
            },
            "type": "text"
          },
          "name": "钥匙ID"
        },
        {
          "identifier": "LockType",
          "dataType": {
            "specs": {
              "1": "指纹",
              "2": "密码",
              "3": "卡",
              "4": "机械钥匙"
            },
            "type": "enum"
          },
          "name": "开锁方式"
        },
        {
          "identifier": "UserLimit",
          "dataType": {
            "specs": {
              "1": "普通用户",
              "2": "管理员",
              "3": "劫持用户"
            },
            "type": "enum"
          },
          "name": "用户权限"
        }
      ],
      "identifier": "KeyAddedNotification",
      "method": "thing.event.KeyAddedNotification.post",
      "name": "添加钥匙通知",
      "type": "info",
      "required": true
    },
    {
      "outputData": [
        {
          "identifier": "KeyID",
          "dataType": {
            "specs": {
              "length": "10"
            },
            "type": "text"
          },
          "name": "钥匙ID"
        },
        {
          "identifier": "LockType",
          "dataType": {
            "specs": {
              "1": "指纹",
              "2": "密码",
              "3": "卡",
              "4": "机械钥匙"
            },
            "type": "enum"
          },
          "name": "开锁方式"
        }
      ],
      "identifier": "KeyDeletedNotification",
      "method": "thing.event.KeyDeletedNotification.post",
      "name": "删除钥匙通知",
      "type": "info",
      "required": true
    },
    {
      "outputData": [
        {
          "identifier": "KeyID",
          "dataType": {
            "specs": {
              "length": "10"
            },
            "type": "text"
          },
          "name": "钥匙ID"
        },
        {
          "identifier": "LockType",
          "dataType": {
            "specs": {
              "1": "指纹",
              "2": "密码",
              "3": "卡",
              "4": "机械钥匙"
            },
            "type": "enum"
          },
          "name": "开锁方式"
        },
        {
          "identifier": "UserLimit",
          "dataType": {
            "specs": {
              "1": "普通用户",
              "2": "管理员",
              "3": "劫持用户"
            },
            "type": "enum"
          },
          "name": "用户权限"
        }
      ],
      "identifier": "KeyInformationNotification",
      "method": "thing.event.KeyInformationNotification.post",
      "name": "钥匙信息上报",
      "type": "info",
      "required": true
    },
    {
      "outputData": [
        {
          "identifier": "KeyID",
          "dataType": {
            "specs": {
              "length": "10"
            },
            "type": "text"
          },
          "name": "钥匙ID"
        },
        {
          "identifier": "LockType",
          "dataType": {
            "specs": {
              "1": "指纹",
              "2": "密码",
              "3": "卡",
              "4": "机械钥匙"
            },
            "type": "enum"
          },
          "name": "开锁方式"
        }
      ],
      "identifier": "DoorOpenNotification",
      "method": "thing.event.DoorOpenNotification.post",
      "name": "开门通知",
      "type": "info",
      "required": true
    },
    {
      "outputData": [
        {
          "identifier": "KeyID",
          "dataType": {
            "specs": {
              "length": "10"
            },
            "type": "text"
          },
          "name": "钥匙ID"
        },
        {
          "identifier": "LockType",
          "dataType": {
            "specs": {
              "1": "指纹",
              "2": "密码",
              "3": "卡",
              "4": "机械钥匙"
            },
            "type": "enum"
          },
          "name": "开锁方式"
        }
      ],
      "identifier": "HijackingAlarm",
      "method": "thing.event.HijackingAlarm.post",
      "name": "劫持报警",
      "type": "info",
      "required": true
    },
    {
      "outputData": [],
      "identifier": "TamperAlarm",
      "method": "thing.event.TamperAlarm.post",
      "name": "防撬报警",
      "type": "info",
      "required": true
    },
    {
      "outputData": [],
      "identifier": "LowElectricityAlarm",
      "method": "thing.event.LowElectricityAlarm.post",
      "name": "低电量报警",
      "type": "info",
      "required": true
    },
    {
      "outputData": [],
      "identifier": "DoorUnlockedAlarm",
      "method": "thing.event.DoorUnlockedAlarm.post",
      "name": "门未锁好报警",
      "type": "info",
      "required": true
    }
  ]
}
