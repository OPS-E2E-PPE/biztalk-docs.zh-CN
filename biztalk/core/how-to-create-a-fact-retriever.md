---
title: 如何创建事实检索器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IFactRetriever interface
- Business Rules Framework, bindings
- factsHandleIn object
- Business Rules Framework, code samples
- Business Rules Framework, fact retrievers
- UpdateFacts method
- Business Rules Framework, programming
ms.assetid: 503dc769-3ada-4099-a5fe-4dd03d995600
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1910d143aaac50d7690c4338c053873f70d2db38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340050"
---
# <a name="how-to-create-a-fact-retriever"></a>如何创建事实检索器
事实检索器是用于在其执行期间添加到策略的长期事实实例的组件。 您可以实现**IFactRetriever**接口，并配置要在运行时使用此实现，以便在长期事实实例中的策略版本。 策略版本调用**UpdateFacts**上每个执行循环，如果事实检索器配置为该特定版本的事实检索器实现的方法。  
  
 您可以选择实现**IFactRemover**事实检索器组件上的接口。 规则引擎将调用**UpdateFactsAfterExecution**方法**IFactRemover**接口时将在释放策略。 这可以执行任何执行后工作，例如提交任何数据库更改或取消任何对象实例的规则引擎工作内存中提供的机会。  
  
## <a name="to-specify-a-fact-retriever-for-a-policy"></a>若要指定策略的事实检索器  
 您可以使用下面的代码配置规则集，使用名为"MyAssembly"作为事实检索器程序集中名为"检索器"的类。  
  
```  
RuleEngineComponentConfiguration fr = new RuleEngineComponentConfiguration("MyAssembly", "Retriever");  
RuleSet rs = new RuleSet("ruleset");  
// associate the execution configuration with a ruleset  
RuleSetExecutionConfiguration rsCfg = rs.ExecutionConfiguration;  
rsCfg.FactRetriever = factRetriever;  
```  
  
> [!NOTE]
>  如果作为 RuleEngineComponentConfiguration 构造函数的第一个参数指定简单程序集名称，如 MyAssembly，则 BizTalk 规则引擎将假定它是私有程序集并查找你的应用程序文件夹中的程序集。 如果指定完全限定的程序集名称，例如**MyAssembly，版本 = 1.0.0.0，区域性 = 中性，PublicKeyToken = a310908b42c024fe**，规则引擎将假定它是共享的程序集并查找在全局程序集程序集缓存 (GAC)。 您可以找到在简单和完全限定的程序集名称的定义[ http://go.microsoft.com/fwlink/?LinkId=64535 ](http://go.microsoft.com/fwlink/?LinkId=64535)。  
  
 您可以设计具有所需的特定于应用程序逻辑，以连接到所需的数据源，断言将数据作为长期事实添加到引擎，并指定刷新或添加到的长期事实数据的新实例的逻辑事实检索器引擎。 直到更新，将在后续的执行循环上使用是最初添加到引擎中并随后缓存的值。 事实检索器实现将返回一个对象，它类似于标记，并可以在连同**factsHandleIn**对象，以确定是否要更新现有事实或添加新的事实。 当策略版本首次调用其事实检索器时**factsHandleIn**对象始终为 null，然后在事实检索器执行之后会返回对象的值。  
  
 请注意，对于相同的规则引擎实例，长期事实只需添加一次。 例如，使用**调用规则**形状在业务流程，该策略实例移动到内部缓存。 在此期间，取消所有短期事实，并保留长期事实。 如果调用同一策略同样，相同的业务流程实例或同一主机中的不同业务流程实例此策略实例是从缓存中提取和重复使用。 在某些批处理环境，可以创建同一策略的多个策略实例。 如果创建新的策略实例，则必须确保添加正确的长期事实。  
  
 此外，你将需要编写自定义代码以实现以下策略：  
  
- 了解何时更新长期事实  
  
- 跟踪的规则引擎所使用的长期事实  
  
  下面的示例代码显示了不同的事实检索器实现，与 MyPolicy 将 mytableinstance 添加为长期事实，使用不同的绑定类型相关联。  
  
## <a name="datatable-binding"></a>DataTable 绑定  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
  
         {  
            SqlDataAdapter dAdapt = new SqlDataAdapter();  
            dAdapt.TableMappings.Add("Table", "CustInfo");  
            SqlConnection conn = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
            conn.Open();  
            SqlCommand myCommand = new SqlCommand("SELECT * FROM CustInfo", conn);  
            myCommand.CommandType = CommandType.Text;  
            dAdapt.SelectCommand = myCommand;  
            DataSet ds = new DataSet("Northwind");  
            dAdapt.Fill(ds);  
            TypedDataTable tdt = new TypedDataTable(ds.Tables["CustInfo"]);  
            engine.Assert(tdt);  
            factsHandleOut = tdt;  
         }  
  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
## <a name="datarow-binding"></a>DataRow 绑定  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
  
         {  
            SqlDataAdapter dAdapt = new SqlDataAdapter();  
            dAdapt.TableMappings.Add("Table", "CustInfo");  
            SqlConnection conn = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
            conn.Open();  
            SqlCommand myCommand = new SqlCommand("SELECT * FROM CustInfo", conn);  
            myCommand.CommandType = CommandType.Text;  
            dAdapt.SelectCommand = myCommand;  
            DataSet ds = new DataSet("Northwind");  
            dAdapt.Fill(ds);  
            TypedDataTable tdt = new TypedDataTable(ds.Tables["CustInfo"]);  
  
            // binding to the first row of CustInfo table  
            TypedDataRow tdr = new TypedDataRow(ds.Tables["CustInfo"].Rows[0],tdt);  
            engine.Assert(tdr);  
            factsHandleOut = tdr;     
         }  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }   
}  
```  
  
 下面的示例代码演示如何添加事实检索器实现中的.NET 和 XML 事实。  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
         {  
            //create .NET object instances  
            bookInstance = new Book();  
            magazineInstance = new Magazine();              
  
            //create an instance of the XML object  
            XmlDocument xd = new XmlDocument();  
  
            //load the document  
            xd.Load(@"..\myXMLInstance.xml");  
  
            //create and instantiate an instance of TXD  
            TypedXmlDocument doc = new TypedXmlDocument("mySchema",xd1);  
  
            engine.Assert(bookInstance);  
            engine.Assert(magazineInstance);  
            engine.Assert(doc);  
            factsHandleOut = doc;  
         }  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
## <a name="dataconnection-binding"></a>DataConnection 绑定  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
  
         {   
            string strCmd = "Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;";  
            SqlConnection conn = new SqlConnection(strCmd);  
            DataConnection dc = new DataConnection("Northwind", "CustInfo", conn);  
  
            engine.Assert(dc);  
            factsHandleOut = dc;           
         }  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
 请注意， **DataConnection**s 应始终重新添加，提供从事实检索器，如上面的代码示例中所示。 引擎实例使用**DataConnection**根据规则条件，查询数据库并由查询返回任何行将其添加到引擎的工作内存中作为**TypedDataRow**s。 Reasserting DataConnection 可以确保在引擎上一次执行中的行，会从内存清除。  
  
 实际上，没有什么优势断言**DataConnection**通过事实检索器，不同之处提供了一种方法来具体化数据源。