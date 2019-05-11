---
title: 如何导入 / 导出和业务策略的部署脚本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, policies
- business rules, deploying
- policies, deploying
- business rules, exporting
- RuleSetDeploymentDriver
- business rules, importing
- Business Rules Framework, policies
- Business Rules Framework, business rules
- Business Rules Framework, code samples
- deploying, business rules
- Business Rules Framework, programming
ms.assetid: 333d37dc-e0ee-460c-922d-70eedf7b7ccb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50358be7c04218321f76b56cb670d1b65f8c9477
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334854"
---
# <a name="how-to-script-import-export-and-deployment-of-business-policies"></a>如何导入 / 导出和业务策略的部署脚本
本部分介绍如何以编程方式导入/导出和部署使用的策略**RuleSetDeploymentDriver**。  
  
 下面的示例演示如何将策略导出到一个文件。  
  
```  
using System;  
using Microsoft.RuleEngine;  
using Microsoft.BizTalk.RuleEngineExtensions;  
namespace SimpleExport  
{  
   class ExportPolicy  
   {  
      [STAThread]  
      static void Main(string[] args)  
      {  
         if (args.Length != 3)  
            Console.WriteLine("Format: PolicyName MajorVersion MinorVersion");  
         else  
         {  
            string policyName = args[0];  
            int majorRev = Convert.ToInt16(args[1]);  
            int minorRev = Convert.ToInt16(args[2]);  
            RuleSetInfo rsi = new RuleSetInfo(policyName,majorRev,minorRev);  
            Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
            dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
                        string fileName = (rsi.Name + "-" + rsi.MajorRevision + "." + rsi.MinorRevision + ".xml");  
            dd.ExportRuleSetToFileRuleStore(rsi,fileName);  
         }  
      }  
   }  
}  
```  
  
 下面的示例演示如何导入和部署策略文件中。  
  
```  
using System;  
using Microsoft.RuleEngine;  
using Microsoft.BizTalk.RuleEngineExtensions;  
namespace SimpleImport  
{  
   class ImportPolicy  
   {  
      [STAThread]  
      static void Main(string[] args)  
      {  
         String filename = args[0];  
         Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
         dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
         SqlRuleStore sqlRuleStore = (SqlRuleStore) dd.GetRuleStore();  
         FileRuleStore fileRuleStore = new FileRuleStore(filename);  
         RuleSetInfoCollection rsic = fileRuleStore.GetRuleSets(RuleStore.Filter.All);  
         foreach (RuleSetInfo rsi in rsic)  
         {  
            RuleSet ruleSet = fileRuleStore.GetRuleSet(rsi);  
            bool publishRuleSets = true;  
            sqlRuleStore.Add(ruleSet,publishRuleSets);  
            dd.Deploy(rsi);  
         }  
      }  
   }  
}    
```  
  
> [!NOTE]
>  该代码假定对词汇; 没有依赖关系如果该策略使用词汇它们必须导入第一次。