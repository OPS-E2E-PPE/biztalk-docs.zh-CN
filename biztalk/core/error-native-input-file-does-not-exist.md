---
title: 错误-本地输入的文件不存在 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.nativeInputFileDoesNotExist
ms.assetid: 17713896-8557-4bf1-b5f0-871b905ae15e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fab62637232795a3cabb15d2ee4830e13e28477a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347334"
---
# <a name="error---native-input-file-does-not-exist"></a>错误-本地输入的文件不存在
**错误代码**  
  
 btm1040  
  
 **说明**  
  
 为测试映射操作指定的本地输入的实例消息文件不存在。 时的值**测试映射输入**映射属性设置为**本机**，必须指定现有的本地实例消息文件**测试映射输入实例**映射属性。  
  
 **用户执行任何操作**  
  
 右键单击解决方案资源管理器中的相关映射，单击**属性**，然后在**测试映射**选项卡中**属性页**对话框的映射，请单击省略号 （**...**) 中的值字段按钮**测试映射输入实例**属性。 在中**选择输入文件**对话框中，选择现有的本机实例与该映射的源架构一致的消息文件。 或者，直接的值字段中键入此本地文件的路径**测试映射输入实例**属性。