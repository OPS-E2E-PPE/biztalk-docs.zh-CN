---
title: 错误-表循环 Functoid 缺少到目标架构的链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingNoLinkToDestSchema
ms.assetid: cf162e6a-5c61-4adc-978b-af641db67ed2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee53c8317b3b5d36c6856123354aab5746d5e84d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346607"
---
# <a name="error---table-looping-functoid-without-link-to-destination-schema"></a>错误-表循环 Functoid 缺少到目标架构的链接
**错误代码**  
  
 btm1077  
  
 **说明**  
  
 与大多数 functoid 不同**表循环**functoid 有多个输出。 除其中一个这些输出必须作为第一个输入参数的单个实例连接**表提取程序**functoid。 剩余的输出必须连接到**记录**目标架构中的节点 （有适当的重复设置）。 此错误发生时这后一种从输出链接**表循环**functoid 缺少。  
  
 **用户执行任何操作**  
  
 将所指示**表循环**记录到适当**记录**要创建缺少的链接的目标架构中的节点。