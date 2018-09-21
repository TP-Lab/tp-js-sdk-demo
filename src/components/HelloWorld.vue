<template>
  <div class="hello">
    <h1>tp-js-sdk-demo v2</h1>
    <div class="item">
      <h3>0. tp.isConnected</h3>
      <div class="demo-content">
        <button @click="isConnected">isConnected</button>
        <div class="isConnectedLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>1.1 tp.getAppInfo</h3>
      <div class="demo-content">
        <button @click="getAppInfo">getAppInfo</button>
        <div class="getAppInfoLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>1.2 tp.getWalletList</h3>
      <div class="demo-content">
        <button @click="getWalletList('eth')">getWalletList(eth)</button>
        <button @click="getWalletList('moac')">getWalletList(moac)</button>
        <button @click="getWalletList('eos')">getWalletList(eos)</button>
        <button @click="getWalletList('enu')">getWalletList(enu)</button>
        <div class="getWalletListLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>1.3 tp.getDeviceId</h3>
      <div class="demo-content">
        <button @click="getDeviceId">getDeviceId</button>
        <div class="getDeviceIdLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>1.4 tp.shareNewsToSNS</h3>
      <div class="demo-content">
        <button @click="shareNewsToSNS">shareNewsToSNS</button>
        <div class="shareNewsToSNSLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>1.5 tp.invokeQRScanner</h3>
      <div class="demo-content">
        <button @click="invokeQRScanner">invokeQRScanner</button>
        <div class="invokeQRScannerLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>1.6 tp.getCurrentWallet</h3>
      <div class="demo-content">
        <button @click="getCurrentWallet">getCurrentWallet</button>
        <div class="getCurrentWalletLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>1.7 tp.getWallets</h3>
      <div class="demo-content">
        
        <textarea style="width:100%" id="push-actions" col="30" rows="2" v-model="getWalletsParams"></textarea><br>
        <button @click="getWallets">getWallets</button>
        <div class="getWalletsLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>1.8 tp.sign</h3>
      <div class="demo-content">
        <textarea style="width:100%" id="push-actions" col="30" rows="2" v-model="appidParams"></textarea><br>
        <button @click="sign">sign</button>
        <div class="signLog">

        </div>
      </div>
    </div>
    <div>
      
      <h3>1.9 tp.eosAuthSign</h3>
      <div class="demo-content">
        <textarea style="width:100%" id="push-actions" col="30" rows="2" v-model="eosAuthSignParams"></textarea><br>
        <button @click="eosAuthSign">eosAuthSign</button>
        <div class="eosAuthSignLog">

        </div>
      </div>
    </div>
    <div>
      
      <h3>1.10 tp.back</h3>
      <div class="demo-content">
        <button @click="gotoBack">下一个页面</button>
      
      </div>
    </div>
     <div>
      
      <h3>1.11 tp.fullScreen</h3>
      <div class="demo-content">
        <button @click="fullScreen(1)">全屏</button>
        <button @click="fullScreen(0)">取消全屏</button>
   
      </div>
    </div>
    <div>
      
      <h3>1.12 tp.close</h3>
      <div class="demo-content">
        <button @click="close">关闭</button>
      </div>
    </div>
  
    <div class="item">
      <h3>2.1 tp.eosTokenTransfer</h3>
      <div class="demo-content">
        <p>from：<input v-model="fromEos" type="text"> </p>
        <p>to: <input v-model="toEos"  type="text" ></p> 
        <p>amount: <input v-model="amountEos"  type="text" ></p> 
        <p>Token: <input v-model="tokenNameEos" type="text"></p>
        <p>Contract: <input v-model="contractEos" type="text"></p>
        <p>precision: <input type="text" v-model="precisionEos"> </p>
        <p>memo: <input  v-model="memoEos" type="text"></p>
        <p>address: <input v-model="addressEos" type="text"> </p>
        <button @click="eosTokenTransfer">eosTokenTransfer</button>
        <div class="eosTokenTransferLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>2.2 tp.pushEosAction</h3>
      <div class="demo-content">
        Change the 'from' and 'to' fields into your custom account at least.
        <textarea style="width:100%" id="push-actions" col="30" rows="10" v-model="actionsEos"></textarea><br>
        <button @click="pushEosAction">pushEosAction</button>
        <div class="pushEosActionLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>2.3 tp.getTableRows</h3>
      <div class="demo-content">
        <textarea style="width:100%" id="push-actions" col="30" rows="5" v-model="eosTableRows"></textarea><br>
        <button @click="getTableRows">getTableRows</button>
        <div class="getTableRowsLog">
        </div>
      </div>
    </div>
    
    <div class="item">
      <h3>2.4 tp.getEosBalance</h3>
      <div class="demo-content">
        <button @click="getEosBalance">getEosBalance</button>
        <div class="getEosBalanceLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>2.5 tp.getEosTransactionRecord</h3>
      <div class="demo-content">
        <textarea style="width:100%" id="push-actions" col="30" rows="5" v-model="eosTransactionParams"></textarea><br>
        <button @click="getEosTransactionRecord">getEosTransactionRecord</button>
        <div class="getEosTransactionRecordLog">
        </div>
      </div>
    </div>
    <div class="item">
      <h3>2.6 tp.getEosAccountInfo</h3>
      <div class="demo-content">
        <button @click="getEosAccountInfo">getEosAccountInfo</button>
        <div class="getEosAccountInfoLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>3.1 tp.moacTokenTransfer</h3>
      <div class="demo-content">
        <p>from：<input v-model="fromMoac" type="text"> </p>
        <p>to: <input v-model="toMoac"  type="text" ></p> 
        <p>amount: <input v-model="amountMoac"  type="text" ></p> 
        <p>tokenName: <input v-model="tokenNameMoac" type="text"></p>
        <p>Contract: <input v-model="contractMoac" type="text"></p>
        <p>decimal: <input type="text" v-model="decimalMoac"> </p>
        <p>gasLimit: <input  v-model="gasLimitMoac" type="text"></p>

        <button @click="moacTokenTransfer">moacTokenTransfer</button>
        <div class="moacTokenTransferLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>3.2 tp.makeTransaction (Deprecated)</h3>
      <div class="demo-content">
        <!-- <button @click="makeTransaction">makeTransaction</button> -->
        <div class="makeTransactionLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>3.3 tp.signTransaction(Deprecated)</h3>
      <div class="demo-content">
        <!-- <button @click="signTransaction">signTransaction</button> -->
        <div class="signTransactionLog">

        </div>
      </div>
    </div>

    <div class="item">
      <h3>4.1 tp.enuTokenTransfer</h3>
      <div class="demo-content">
        <p>from：<input v-model="fromEnu" type="text"> </p>
        <p>to: <input v-model="toEnu"  type="text" ></p> 
        <p>amount: <input v-model="amountEnu"  type="text" ></p> 
        <p>Token: <input v-model="tokenNameEnu" type="text"></p>
        <p>Contract: <input v-model="contractEnu" type="text"></p>
        <p>precision: <input type="text" v-model="precisionEnu"> </p>
        <p>memo: <input  v-model="memoEnu" type="text"></p>
        <p>address: <input v-model="addressEnu" type="text"> </p>
        <button @click="enuTokenTransfer">enuTokenTransfer</button>
        <div class="enuTokenTransferLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>4.2 tp.pushEnuAction</h3>
      <div class="demo-content">
        Change the 'from' and 'to' fields into your custom account at least.
        <textarea style="width:100%" id="push-actions" col="30" rows="10" v-model="actionsEnu"></textarea><br>
        <button @click="pushEnuAction">pushEnuAction</button>
        <div class="pushEnuActionLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>4.3 tp.getEnuTableRows</h3>
      <div class="demo-content">
        <textarea style="width:100%" id="push-actions" col="30" rows="5" v-model="enuTableRows"></textarea><br>
        <button @click="getEnuTableRows">getEnuTableRows</button>
        <div class="getEnuTableRowsLog">
        </div>
      </div>
    </div>
    
    <div class="item">
      <h3>4.4 tp.getEnuBalance</h3>
      <div class="demo-content">
        <button @click="getEnuBalance">getEnuBalance</button>
        <div class="getEnuBalanceLog">

        </div>
      </div>
    </div>
    <div class="item">
      <h3>4.5 tp.getEnuTransactionRecord</h3>
      <div class="demo-content">
        <textarea style="width:100%" id="push-actions" col="30" rows="5" v-model="enuTransactionParams"></textarea><br>
        <button @click="getEnuTransactionRecord">getEnuTransactionRecord</button>
        <div class="getEnuTransactionRecordLog">
        </div>
      </div>
    </div>
    <div class="item">
      <h3>4.6 tp.getEnuAccountInfo</h3>
      <div class="demo-content">
        <button @click="getEnuAccountInfo">getEnuAccountInfo</button>
        <div class="getEnuAccountInfoLog">

        </div>
      </div>
    </div>

    
  </div>
</template>

<script>
import tp from 'tp-js-sdk';
import $ from 'jquery';

export default {
  name: 'HelloWorld',
  data () {
    return {
      fromEos: '',
      toEos: '',
      amountEos: '',
      contractEos: '',
      tokenNameEos: '',
      addressEos: '',
      precisionEos: '',
      memoEos: '',
      fromEnu: '',
      toEnu: '',
      amountEnu: '',
      contractEnu: '',
      tokenNameEnu: '',
      addressEnu: '',
      precisionEnu: '',
      memoEnu: '',
      fromMoac: '',
      toMoac: '',
      amountMoac: '',
      contractMoac: '',
      tokenNameMoac: '',
      decimalMoac: '',
      gasLimitMoac: '',
      getWalletsParams: '{"permission": "active", "blockchain": "eos"}',
      appidParams: '{"appid": "s9QY7ZYad6Xm"}',
      eosAuthSignParams: '{"from": "itokenpocket", "publicKey": "abc", "signdata": "abc"}',
      eosTransactionParams: '{"start": 2, "account": "itokenpocket", "count": 20, "token": "EOS", "sort": "desc", "contract": "eosio.token"}',
      eosTableRows: '{"json": true, "code": "theeosbutton", "scope": "theeosbutton","table": "accstates","lower_bound": "10", "limit": 30}',
      actionsEos: '{"actions":[{"account":"eosio.token","name":"transfer","authorization":[{"actor":"itokenpocket","permission":"active"}],"data":{"from":"itokenpocket","to":"itokenpocket","quantity":"0.0001 EOS","memo":"test sdk"}},{"account":"eosio","name":"delegatebw","authorization":[{"actor":"itokenpocket","permission":"active"}],"data":{"from":"itokenpocket","receiver":"itokenpocket","stake_net_quantity":"0.0100 EOS","stake_cpu_quantity":"0.0100 EOS","transfer":0}}],"account": "itokenpocket", "address": "EOS7ds9A9FGDsKrdymQ4ynKbMgbCVUdBsosEpsLTqvg6icyBMcQUm"}',
      enuTransactionParams: '{"start": 2, "account": "accommodated", "count": 20, "token": "ENU", "sort": "desc", "contract": "enu.token"}',
      enuTableRows: '{"json": true, "code": "pickpickteam", "scope": "pickpickteam","table": "question","lower_bound": "5", "limit": 8}',
      actionsEnu: '{"actions":[{"account":"enu.token","name":"transfer","authorization":[{"actor":"accommodated","permission":"active"}],"data":{"from":"accommodated","to":"accommodated","quantity":"0.0001 ENU","memo":"test sdk"}},{"account":"enumivo","name":"delegatebw","authorization":[{"actor":"accommodated","permission":"active"}],"data":{"from":"accommodated","receiver":"accommodated","stake_net_quantity":"0.0100 ENU","stake_cpu_quantity":"0.0100 ENU","transfer":0}}], "account": "accommodated", "address": "ENU58Y6KWWVTa3nGVgPmAWyxAXJoyy7kkKjbStPW5C63QJdYJ1TtP"}'
    }
  },
  created() {
    window.tp = tp;
    console.log(tp);

  },
  methods: {
    isConnected() {
      $('.isConnectedLog').append('' + tp.isConnected());
    },
    getAppInfo() {
      tp.getAppInfo().then(data =>{
        $('.getAppInfoLog').append(JSON.stringify(data));
      })
    },
    getWalletList(params) {
      tp.getWalletList(params).then(data => {
        $('.getWalletListLog').append(JSON.stringify(data));
      })
    },
    getDeviceId() {
      tp.getDeviceId().then(data => {
        $('.getDeviceIdLog').append(JSON.stringify(data));
      })
    },
    getWallets() {
      var params = JSON.parse(this.getWalletsParams);
      $('.getWalletsLog').append(JSON.stringify(params));
      
      tp.getWallets(params).then(data => {
        $('.getWalletsLog').append(JSON.stringify(data));
      })
    },
    shareNewsToSNS() {
      tp.shareNewsToSNS({
        title: 'TokenPocket',
        desc: 'Your Universal Wallet',
        url: 'https://www.mytokenpocket.vip/',
        previewImage: ''
      }).then(data => {
        $('.shareNewsToSNSLog').append(JSON.stringify(data));
      })
    },
    invokeQRScanner() {
      tp.invokeQRScanner().then(data => {
        $('.invokeQRScannerLog').append(JSON.stringify(data));
      })
    },
    getCurrentWallet() {
      tp.getCurrentWallet().then(data => {
        $('.getCurrentWalletLog').append(JSON.stringify(data));
      })
    },
    sign() {
      var params = JSON.parse(this.appidParams);
      $('.signLog').append(JSON.stringify(params));
      tp.sign(params).then(data => {
        $('.signLog').append(JSON.stringify(data));
      })
    },
    fullScreen(num) {
      tp.fullScreen({fullScreen: +num});
    },
    gotoBack() {
      this.$router.push('/back');
    },
    close() {
      tp.close();
    },
    eosAuthSign() {
      var params = JSON.parse(this.eosAuthSignParams);
      $('.eosAuthSignLog').append(JSON.stringify(params));
      tp.eosAuthSign(params).then(data => {
        $('.eosAuthSignLog').append(JSON.stringify(data));
      })
    },
    eosTokenTransfer() {
      var params = {
        from: this.fromEos,
        to: this.toEos,
        amount: this.amountEos,
        contract: this.contractEos,
        precision: this.precisionEos,
        memo: this.memoEos,
        tokenName: this.tokenNameEos,
        address: this.addressEos,
      }
      $('.eosTokenTransferLog').append(JSON.stringify(params));
      tp.eosTokenTransfer(params).then(data => {
        $('.eosTokenTransferLog').append(JSON.stringify(data));
      })
    },
    pushEosAction() {
      try {
        var params = JSON.parse(this.actionsEos);

        tp.pushEosAction(params).then(data => {
          $('.pushEosActionLog').append(JSON.stringify(data));
        })
      }
      catch(e) {
        console.log(e);
      }
      
    },
    getTableRows() {
      try {
        var params = JSON.parse(this.eosTableRows);

        tp.getTableRows(params).then(data => {
          $('.getTableRowsLog').append(JSON.stringify(data));
        });
      }
      catch(e) {
        console.log(e);
      }
    },
    getEosTransactionRecord() {
      try {
        var params = JSON.parse(this.eosTransactionParams);

        tp.getEosTransactionRecord(params).then(data => {
          $('.getEosTransactionRecordLog').append(JSON.stringify(data));
        });
      }
      catch(e) {
        console.log(e);
      }
    },
   
    getEosBalance() {
      var params = {
        account: 'itokenpocket',
        contract: 'eosadddddddd', 
        symbol: 'AD'
      }
      $('.getEosBalanceLog').append(JSON.stringify(params));
      tp.getEosBalance(params).then(data => {
        $('.getEosBalanceLog').append(JSON.stringify(data));
      })
    },
    getEosAccountInfo() {
      var params = {
        account: 'itokenpocket'
      }
      $('.getEosAccountInfoLog').append(JSON.stringify(params));
      tp.getEosAccountInfo(params).then(data => {
        $('.getEosAccountInfoLog').append(JSON.stringify(data));
      })
    },


    // enu
    enuTokenTransfer() {
      var params = {
        from: this.fromEnu,
        to: this.toEnu,
        amount: this.amountEnu,
        contract: this.contractEnu,
        precision: this.precisionEnu,
        memo: this.memoEnu,
        tokenName: this.tokenNameEnu,
        address: this.addressEnu
      }
      $('.enuTokenTransferLog').append(JSON.stringify(params));
      tp.enuTokenTransfer(params).then(data => {
        $('.enuTokenTransferLog').append(JSON.stringify(data));
      })
    },
    pushEnuAction() {
      try {
        var params = JSON.parse(this.actionsEnu);

        tp.pushEnuAction(params).then(data => {
          $('.pushEnuActionLog').append(JSON.stringify(data));
        })
      }
      catch(e) {
        console.log(e);
      }
      
    },
    getEnuTableRows() {
      try {
        var params = JSON.parse(this.enuTableRows);

        tp.getEnuTableRows(params).then(data => {
          $('.getEnuTableRowsLog').append(JSON.stringify(data));
        });
      }
      catch(e) {
        console.log(e);
      }
    },
    getEnuTransactionRecord() {
      try {
        var params = JSON.parse(this.enuTransactionParams);

        tp.getEnuTransactionRecord(params).then(data => {
          $('.getEnuTransactionRecordLog').append(JSON.stringify(data));
        });
      }
      catch(e) {
        console.log(e);
      }
    },
    getEnuBalance() {
      var params = {
        account: 'accommodated',
        contract: 'ltsonenumivo', 
        symbol: 'LTS'
      }
      $('.getEnuBalanceLog').append(JSON.stringify(params));
      tp.getEnuBalance(params).then(data => {
        $('.getEnuBalanceLog').append(JSON.stringify(data));
      })
    },
    getEnuAccountInfo() {
      var params = {
        account: 'accommodated'
      }
      $('.getEnuAccountInfoLog').append(JSON.stringify(params));
      tp.getEnuAccountInfo(params).then(data => {
        $('.getEnuAccountInfoLog').append(JSON.stringify(data));
      })
    },

    // moac eth
    moacTokenTransfer() {
      var params = {
        from: this.fromMoac,
        to: this.toMoac,
        amount: this.amountMoac,
        contract: this.contractMoac,
        decimal: this.decimalMoac,
        gasLimit: this.gasLimitMoac,
        tokenName: this.tokenNameMoac
      }
      $('.moacTokenTransferLog').append(JSON.stringify(params));
      tp.moacTokenTransfer(params).then(data => {
        $('.moacTokenTransferLog').append(JSON.stringify(data));
      })
    },
    makeTransaction() {
      tp.makeTransaction().then(data => {
        $('.makeTransactionLog').append(JSON.stringify(data));
      })
    },
    signTransaction() {
      tp.signTransaction().then(data => {
        $('.signTransactionLog').append(JSON.stringify(data));
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
button {
  padding: 4px 10px;
  -webkit-appearance: none;
  border: 1px solid #ddd;
  border-radius: 2px;
  background: #fff;
  line-height: 1.5;
}
div, p {
  word-break: break-all;
}

.item {
    border-bottom: 1px solid #f1f1f1;
    padding: 20px 10px;
}
</style>
