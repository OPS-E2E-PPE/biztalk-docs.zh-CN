---
title: 如何创建事实检索器 |Microsoft 文档
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
ms.openlocfilehash: 20ea60356580ae7d5a6ac2be3336ec07314211f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250205"
---
# <a name="how-to-create-a-fact-retriever"></a><span data-ttu-id="fe52f-102">如何创建事实检索器</span><span class="sxs-lookup"><span data-stu-id="fe52f-102">How to Create a Fact Retriever</span></span>
<span data-ttu-id="fe52f-103">事实检索器是在策略执行期间用来将长期事实实例添加到该策略中的组件。</span><span class="sxs-lookup"><span data-stu-id="fe52f-103">A fact retriever is a component that is used to assert instances of long-term facts into a policy during its execution.</span></span> <span data-ttu-id="fe52f-104">你可以实现**IFactRetriever**接口，并配置为策略版本，以在运行时使用此实现，以使保持长期的事实实例。</span><span class="sxs-lookup"><span data-stu-id="fe52f-104">You can implement the **IFactRetriever** interface and configure a policy version to use this implementation at run time to bring in the long-term fact instances.</span></span> <span data-ttu-id="fe52f-105">策略版本时，将调用**UpdateFacts**上每个执行周期，如果事实检索器配置为该特定版本的事实检索器实现的方法。</span><span class="sxs-lookup"><span data-stu-id="fe52f-105">The policy version invokes the **UpdateFacts** method of the fact retriever implementation on every execution cycle, if a fact retriever is configured for that particular version.</span></span>  
  
 <span data-ttu-id="fe52f-106">你可以选择实现**IFactRemover**事实检索器组件上的接口。</span><span class="sxs-lookup"><span data-stu-id="fe52f-106">You can optionally implement the **IFactRemover** interface on a fact retriever component.</span></span> <span data-ttu-id="fe52f-107">规则引擎时，将调用**UpdateFactsAfterExecution**方法**IFactRemover**接口时释放策略。</span><span class="sxs-lookup"><span data-stu-id="fe52f-107">The rule engine invokes the **UpdateFactsAfterExecution** method of the **IFactRemover** interface when the policy is disposed.</span></span> <span data-ttu-id="fe52f-108">这使您可以有机会进行执行后工作，例如提交任何数据库更改或从规则引擎的工作内存取消任何对象实例。</span><span class="sxs-lookup"><span data-stu-id="fe52f-108">This provides an opportunity to you to do any post-execution work such as committing any database changes or retracting any object instances from the rule engine's working memory.</span></span>  
  
## <a name="to-specify-a-fact-retriever-for-a-policy"></a><span data-ttu-id="fe52f-109">为策略指定事实检索器</span><span class="sxs-lookup"><span data-stu-id="fe52f-109">To specify a fact retriever for a policy</span></span>  
 <span data-ttu-id="fe52f-110">您可以使用以下代码配置规则集，使用“MyAssembly”程序集中的“Retriever”类作为事实检索器。</span><span class="sxs-lookup"><span data-stu-id="fe52f-110">You could use the following code to configure the rule set to use a class named "Retriever" in the assembly named "MyAssembly" as the fact retriever.</span></span>  
  
```  
RuleEngineComponentConfiguration fr = new RuleEngineComponentConfiguration("MyAssembly", "Retriever");  
RuleSet rs = new RuleSet("ruleset");  
// associate the execution configuration with a ruleset  
RuleSetExecutionConfiguration rsCfg = rs.ExecutionConfiguration;  
rsCfg.FactRetriever = factRetriever;  
```  
  
> [!NOTE]
>  <span data-ttu-id="fe52f-111">如果指定简单程序集名称（如 MyAssembly）作为 RuleEngineComponentConfiguration 构造函数的第一个参数，则 BizTalk 规则引擎将假定它是私有程序集，并在应用程序文件夹中查找该程序集。</span><span class="sxs-lookup"><span data-stu-id="fe52f-111">If you specify simple assembly name such as MyAssembly as the first parameter for RuleEngineComponentConfiguration constructor, the BizTalk rule engine assumes that it is a private assembly and looks for the assembly in your application folder.</span></span> <span data-ttu-id="fe52f-112">如果指定完全限定程序集名称，如**MyAssembly，Version = 1.0.0.0，Culture = neutral，PublicKeyToken = a310908b42c024fe**，规则引擎假定它是共享的程序集，查找在全局程序集程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="fe52f-112">If you specify fully qualified assembly name such as **MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=a310908b42c024fe**, the rule engine assumes that it is a shared assembly and looks for the assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="fe52f-113">你可以找到在简单和完全限定的程序集名称的定义[http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535)。</span><span class="sxs-lookup"><span data-stu-id="fe52f-113">You can find the definitions of simple and fully qualified assembly names at [http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535).</span></span>  
  
 <span data-ttu-id="fe52f-114">您可以使用所需的特定于应用程序的逻辑来设计事实检索器以连接所需的数据源，将该数据作为长期事实添加到到引擎中，并指定刷新或向引擎中添加新的长期事实实例的逻辑。</span><span class="sxs-lookup"><span data-stu-id="fe52f-114">You can design the fact retriever with the required application-specific logic to connect to the required data sources, assert the data as long-term facts into the engine, and specify the logic for refreshing or asserting new instances of the long-term facts into the engine.</span></span> <span data-ttu-id="fe52f-115">只有在更新之后，最初添加到引擎中并随后缓存的值才将用于后续的执行循环。</span><span class="sxs-lookup"><span data-stu-id="fe52f-115">Until updated, the values that are initially asserted into the engine and consequently cached will be used on subsequent execution cycles.</span></span> <span data-ttu-id="fe52f-116">事实检索器实现返回一个对象，它类似于一个令牌，并可用于沿**factsHandleIn**对象来确定是否要更新现有的事实数据或断言新事实。</span><span class="sxs-lookup"><span data-stu-id="fe52f-116">The fact retriever implementation returns an object that is analogous to a token and can be used along with the **factsHandleIn** object to determine whether to update existing facts or assert new facts.</span></span> <span data-ttu-id="fe52f-117">当策略版本首次调用其事实检索器**factsHandleIn**对象始终为 null，然后将在之后的事实检索执行返回的对象的值。</span><span class="sxs-lookup"><span data-stu-id="fe52f-117">When a policy version calls its fact retriever for the first time, the **factsHandleIn** object is always null and then takes the value of the return object after the fact retriever's execution.</span></span>  
  
 <span data-ttu-id="fe52f-118">请注意，对于同一规则引擎实例，一个长期事实只需添加一次。</span><span class="sxs-lookup"><span data-stu-id="fe52f-118">Note that for the same rule engine instance, a long-term fact only needs to be asserted once.</span></span> <span data-ttu-id="fe52f-119">例如，当使用**调用规则**形状中业务流程、 策略实例移动到内部缓存。</span><span class="sxs-lookup"><span data-stu-id="fe52f-119">For example, when you use the **Call Rules** shape in an orchestration, the policy instance is moved into an internal cache.</span></span> <span data-ttu-id="fe52f-120">此时，将取消所有短期事实，并保留所有长期事实。</span><span class="sxs-lookup"><span data-stu-id="fe52f-120">At this time, all short-term facts are retracted and long-term facts are kept.</span></span> <span data-ttu-id="fe52f-121">如果同一策略由同一业务流程实例或同一主机中的不同业务流程实例再次调用，则将从缓存中提取此策略实例并重新使用。</span><span class="sxs-lookup"><span data-stu-id="fe52f-121">If the same policy is called again, either by the same orchestration instance or by a different orchestration instance in the same host, this policy instance is fetched from the cache and reused.</span></span> <span data-ttu-id="fe52f-122">在某些批处理环境中，可以创建同一策略的多个策略实例。</span><span class="sxs-lookup"><span data-stu-id="fe52f-122">In some batch processing scenarios, several policy instances of the same policy could be created.</span></span> <span data-ttu-id="fe52f-123">如果创建新的策略实例，则必须确保添加了正确的长期事实。</span><span class="sxs-lookup"><span data-stu-id="fe52f-123">If a new policy instance is created, you must ensure that the correct long-term facts are asserted.</span></span>  
  
 <span data-ttu-id="fe52f-124">此外，您需要编写自定义代码以实现以下策略：</span><span class="sxs-lookup"><span data-stu-id="fe52f-124">Additionally, you would need to write custom code to implement the following strategies:</span></span>  
  
-   <span data-ttu-id="fe52f-125">了解何时更新长期事实</span><span class="sxs-lookup"><span data-stu-id="fe52f-125">Know when to update the long-term facts</span></span>  
  
-   <span data-ttu-id="fe52f-126">跟踪规则引擎所使用的长期事实</span><span class="sxs-lookup"><span data-stu-id="fe52f-126">Keep track of which rule engine instance uses which long-term facts</span></span>  
  
 <span data-ttu-id="fe52f-127">下面的示例代码显示了不同的事实检索器实现，它们使用不同的绑定类型与 MyPolicy 相关联以将 MyTableInstance 添加为长期事实。</span><span class="sxs-lookup"><span data-stu-id="fe52f-127">The following sample code shows different fact retriever implementations, which are associated with MyPolicy to assert MyTableInstance as a long-term fact, using different binding types.</span></span>  
  
## <a name="datatable-binding"></a><span data-ttu-id="fe52f-128">DataTable 绑定</span><span class="sxs-lookup"><span data-stu-id="fe52f-128">DataTable binding</span></span>  
  
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
  
## <a name="datarow-binding"></a><span data-ttu-id="fe52f-129">DataRow 绑定</span><span class="sxs-lookup"><span data-stu-id="fe52f-129">DataRow binding</span></span>  
  
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
  
 <span data-ttu-id="fe52f-130">下面的示例代码演示了如何在事实检索器实现中添加 .NET 和 XML 事实。</span><span class="sxs-lookup"><span data-stu-id="fe52f-130">The following sample code demonstrates how to assert .NET and XML facts in a fact retriever implementation.</span></span>  
  
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
  
## <a name="dataconnection-binding"></a><span data-ttu-id="fe52f-131">DataConnection 绑定</span><span class="sxs-lookup"><span data-stu-id="fe52f-131">DataConnection Binding</span></span>  
  
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
  
 <span data-ttu-id="fe52f-132">请注意，**该组**s 应始终 reasserted 时提供从事实检索器，如上面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="fe52f-132">Note that **DataConnection**s should always be reasserted, when provided from a fact retriever, as shown in the preceding code sample.</span></span> <span data-ttu-id="fe52f-133">引擎实例使用**该组**基于规则条件中，在数据库中查询和查询返回的任何行将断言到引擎的工作内存**TypedDataRow**s。</span><span class="sxs-lookup"><span data-stu-id="fe52f-133">The engine instance uses the **DataConnection** to query the database based on the rule conditions, and any rows returned by the query would be asserted into the engine's working memory as **TypedDataRow**s.</span></span> <span data-ttu-id="fe52f-134">Reasserting 数据连接可确保从引擎上一次执行的行从内存中清除。</span><span class="sxs-lookup"><span data-stu-id="fe52f-134">Reasserting the DataConnection ensures that rows from a previous execution of the engine are cleared from memory.</span></span>  
  
 <span data-ttu-id="fe52f-135">实际上，没有什么好处到断言**该组**通过一个事实，不同之处检索器使您能够外部化的数据源。</span><span class="sxs-lookup"><span data-stu-id="fe52f-135">In fact, there is little advantage to asserting a **DataConnection** through a fact retriever except that it provides a way to externalize the data source.</span></span>