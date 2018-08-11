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
      <h3>2.1 tp.eosTokenTransfer</h3>
      <div class="demo-content">
        <p>from：<input v-model="fromEos" type="text"> </p>
        <p>to: <input v-model="toEos"  type="text" ></p> 
        <p>amount: <input v-model="amountEos"  type="text" ></p> 
        <p>Token: <input v-model="tokenNameEos" type="text"></p>
        <p>Contract: <input v-model="contractEos" type="text"></p>
        <p>precision: <input type="text" v-model="precisionEos"> </p>
        <p>memo: <input  v-model="memoEos" type="text"></p>
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
        <textarea style="width:100%" id="push-actions" col="30" rows="5" v-model="tableRows"></textarea><br>
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
    <!-- <div class="item">
      <h3>2.5 tp.getEosTransactionRecord (ios 0.37+ , android 0.42+)</h3>
      <div class="demo-content">
        <textarea style="width:100%" id="push-actions" col="30" rows="5" v-model="transactionParams"></textarea><br>
        <button @click="getEosTransactionRecord">getEosTransactionRecord</button>
        <div class="getEosTransactionRecordLog">
        </div>
      </div>
    </div> -->
    <div class="item">
      <h3>2.6 tp.getEosAccountInfo (ios 0.37+ , android 0.42+)</h3>
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
      precisionEos: '',
      memoEos: '',
      fromMoac: '',
      toMoac: '',
      amountMoac: '',
      contractMoac: '',
      tokenNameMoac: '',
      decimalMoac: '',
      gasLimitMoac: '',
      transactionParams: '{"page": 2, "account": "itokenpocket", "count": 20, "token": "EOS", "sort": "desc", "contract": "eosio.token"}',
      tableRows: '{"json": true, "code": "theeosbutton", "scope": "theeosbutton","table": "accstates","lower_bound": "10", "limit": 30}',
      actionsEos: '{"actions":[{"account":"eosio.token","name":"transfer","authorization":[{"actor":"itokenpocket","permission":"active"}],"data":{"from":"itokenpocket","to":"itokenpocket","quantity":"0.0001 EOS","memo":"test sdk"}},{"account":"eosio","name":"delegatebw","authorization":[{"actor":"itokenpocket","permission":"active"}],"data":{"from":"itokenpocket","receiver":"itokenpocket","stake_net_quantity":"0.0100 EOS","stake_cpu_quantity":"0.0100 EOS","transfer":0}}]}'
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
    eosTokenTransfer() {
      var params = {
        from: this.fromEos,
        to: this.toEos,
        amount: this.amountEos,
        contract: this.contractEos,
        precision: this.precisionEos,
        memo: this.memoEos,
        tokenName: this.tokenNameEos
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
        var params = JSON.parse(this.tableRows);

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
        var params = JSON.parse(this.transactionParams);

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
