xml xmlns="http://www.w3.org/1999/xhtml" collection="false">
  <variables>
    <variable type="" id="W4$:ZQCmEz#8+=4ysv5Y">stop loss</variable>
    <variable type="" id="j}8O`Vs+RJljIwPu-_:_">initial amount</variable>
    <variable type="" id="mXtFswo{p,|%W1:V-$+r">profit</variable>
    <variable type="" id="%L?;380E6Lr^3b.%}t5Q">win amount</variable>
    <variable type="" id="r;j5hdLRm`b6LFCDue7-">martingale</variable>
  </variables>
  <block type="trade" id="trade" x="-4" y="-45">
    <field name="MARKET_LIST">synthetic_index</field>
    <field name="SUBMARKET_LIST">random_index</field>
    <field name="SYMBOL_LIST">R_100</field>
    <field name="TRADETYPECAT_LIST">digits</field>
    <field name="TRADETYPE_LIST">matchesdiffers</field>
    <field name="TYPE_LIST">DIGITDIFF</field>
    <field name="CANDLEINTERVAL_LIST">60</field>
    <field name="TIME_MACHINE_ENABLED">FALSE</field>
    <field name="RESTARTONERROR">TRUE</field>
    <statement name="INITIALIZATION">
      <block type="text_print" id="EDivDExvOQkw/~i;V+j8">
        <value name="TEXT">
          <shadow type="text" id="kv+MPF!f)#C[?TCT^dS(">
            <field name="TEXT">candle mine version 2</field>
          </shadow>
        </value>
        <next>
          <block type="variables_set" id="IpH/OKA3R.E;dEgGMbf,">
            <field name="VAR" id="W4$:ZQCmEz#8+=4ysv5Y" variabletype="">stop loss</field>
            <value name="VALUE">
              <block type="math_number" id="=XFKCMq#6s#Mo6`~.@`0">
                <field name="NUM">9999</field>
              </block>
            </value>
            <next>
              <block type="variables_set" id="{_clcmJ(*gEi!Br8c}kM">
                <field name="VAR" id="mXtFswo{p,|%W1:V-$+r" variabletype="">profit</field>
                <value name="VALUE">
                  <block type="math_number" id="q}((XO%dDMm1RXxPNqt#">
                    <field name="NUM">9999</field>
                  </block>
                </value>
                <next>
                  <block type="variables_set" id=")ZZGf^cT0rOqa/Ma%NC]">
                    <field name="VAR" id="j}8O`Vs+RJljIwPu-_:_" variabletype="">initial amount</field>
                    <value name="VALUE">
                      <block type="math_number" id="YHAI}G~p-MzbG{Q#}HYP">
                        <field name="NUM">110</field>
                      </block>
                    </value>
                    <next>
                      <block type="variables_set" id="su0Gc91D[(`K},Nk5p|N">
                        <field name="VAR" id="%L?;380E6Lr^3b.%}t5Q" variabletype="">win amount</field>
                        <value name="VALUE">
                          <block type="math_number" id="MFliyze83ZUSaeqHp]Qd">
                            <field name="NUM">110</field>
                          </block>
                        </value>
                        <next>
                          <block type="variables_set" id="Ca6FIrM?^n2xEd$bl0|T">
                            <field name="VAR" id="r;j5hdLRm`b6LFCDue7-" variabletype="">martingale</field>
                            <value name="VALUE">
                              <block type="math_number" id="$G_m![15Q+*L1xvo!K@.">
                                <field name="NUM">11</field>
                              </block>
                            </value>
                          </block>
                        </next>
                      </block>
                    </next>
                  </block>
                </next>
              </block>
            </next>
          </block>
        </next>
      </block>
    </statement>
    <statement name="SUBMARKET">
      <block type="tradeOptions" id="e9H9Aque*t_l]hki@?v1">
        <field name="DURATIONTYPE_LIST">t</field>
        <field name="CURRENCY_LIST">USD</field>
        <field name="BARRIEROFFSETTYPE_LIST">+</field>
        <field name="SECONDBARRIEROFFSETTYPE_LIST">-</field>
        <value name="DURATION">
          <block type="math_number" id="~G^:]=.b`!T9.Il_vkLS">
            <field name="NUM">1</field>
          </block>
        </value>
        <value name="AMOUNT">
          <block type="variables_get" id="U7j6VStMd;ipx]Ouc..l">
            <field name="VAR" id="j}8O`Vs+RJljIwPu-_:_" variabletype="">initial amount</field>
          </block>
        </value>
        <value name="PREDICTION">
          <block type="last_digit" id="??5v2gCRvFhdio`k9/HO"></block>
        </value>
      </block>
    </statement>
  </block>
  <block type="text" id="3mdAU?=Tbm-T@3=*EqH$" disabled="true" x="0" y="544">
    <field name="TEXT">STILL</field>
  </block>
  <block type="during_purchase" id="4/HZDK).D8=^Cv4C^vT4" collapsed="true" x="0" y="595"></block>
  <block type="after_purchase" id="finish" x="0" y="648">
    <statement name="AFTERPURCHASE_STACK">
      <block type="controls_if" id="a!_WKGNJh,yQ}tk|:`NI">
        <mutation else="1"></mutation>
        <value name="IF0">
          <block type="contract_check_result" id="O1ON.Ffb1!6t,P`iFZ]!">
            <field name="CHECK_RESULT">win</field>
          </block>
        </value>
        <statement name="DO0">
          <block type="notify" id="zw:P~.RrRR4@/[ZDu;Cc">
            <field name="NOTIFICATION_TYPE">success</field>
            <field name="NOTIFICATION_SOUND">silent</field>
            <value name="MESSAGE">
              <block type="text_join" id="6v3if%7]E52#?`jFIB!f">
                <mutation items="2"></mutation>
                <value name="ADD0">
                  <block type="text" id="ODDvC.!;oC7lFi#W0*kB">
                    <field name="TEXT">Ganhou: </field>
                  </block>
                </value>
                <value name="ADD1">
                  <block type="read_details" id="KzeETsb#x.wDkbkAPd=}">
                    <field name="DETAIL_INDEX">4</field>
                  </block>
                </value>
              </block>
            </value>
            <next>
              <block type="variables_set" id="=*k@},WThq4c@/K_{kF%">
                <field name="VAR" id="j}8O`Vs+RJljIwPu-_:_" variabletype="">initial amount</field>
                <value name="VALUE">
                  <block type="variables_get" id="zaeP]S1q0DLSb08yz]+4">
                    <field name="VAR" id="%L?;380E6Lr^3b.%}t5Q" variabletype="">win amount</field>
                  </block>
                </value>
              </block>
            </next>
          </block>
        </statement>
        <statement name="ELSE">
          <block type="notify" id="%oq)w)m2-uXUJwDkEX3r">
            <field name="NOTIFICATION_TYPE">warn</field>
            <field name="NOTIFICATION_SOUND">silent</field>
            <value name="MESSAGE">
              <block type="text_join" id="kRD-eN4Qav7`u.gQ(tkn">
                <mutation items="2"></mutation>
                <value name="ADD0">
                  <block type="text" id="_u}p#WG2-0R,3wmR::e7">
                    <field name="TEXT">Perdeu: </field>
                  </block>
                </value>
                <value name="ADD1">
                  <block type="math_single" id="WC8^:q6MT;.=}juq3~w+">
                    <field name="OP">ABS</field>
                    <value name="NUM">
                      <shadow type="math_number" id="GleSn`9j7Cm7/dqg}FIA">
                        <field name="NUM">9</field>
                      </shadow>
                      <block type="read_details" id="[6yQUMvdZh#*SBr)o1Lf">
                        <field name="DETAIL_INDEX">4</field>
                      </block>
                    </value>
                  </block>
                </value>
              </block>
            </value>
            <next>
              <block type="math_change" id="szxi%pOMsEZiNe!@=`z_">
                <field name="VAR" id="j}8O`Vs+RJljIwPu-_:_" variabletype="">initial amount</field>
                <value name="DELTA">
                  <shadow type="math_number" id="N=Vo^MVz~/^(xt7Ag@8E">
                    <field name="NUM">1</field>
                  </shadow>
                  <block type="math_arithmetic" id="L|Yp}u1YlBQ9k78`pWjV">
                    <field name="OP">MULTIPLY</field>
                    <value name="A">
                      <shadow type="math_number" id="ka8n8|Dugz,q5FkUjs`7">
                        <field name="NUM">1</field>
                      </shadow>
                      <block type="math_single" id="FX_=g~%((pbM8DTsJlMU">
                        <field name="OP">ABS</field>
                        <value name="NUM">
                          <shadow type="math_number" id="GleSn`9j7Cm7/dqg}FIA">
                            <field name="NUM">9</field>
                          </shadow>
                          <block type="read_details" id="E^S1f%ov/wT*)f}Q2!SK">
                            <field name="DETAIL_INDEX">4</field>
                          </block>
                        </value>
                      </block>
                    </value>
                    <value name="B">
                      <shadow type="math_number" id="{JXdZCp2%s=sfO@yN:n}">
                        <field name="NUM">1</field>
                      </shadow>
                      <block type="variables_get" id="IC~rt2?ZPHW|/zz-/hF=">
                        <field name="VAR" id="r;j5hdLRm`b6LFCDue7-" variabletype="">martingale</field>
                      </block>
                    </value>
                  </block>
                </value>
                <next>
                  <block type="controls_if" id="mu#-HM%oPx={kJ=fV8=|">
                    <value name="IF0">
                      <block type="logic_compare" id="dNs]t(GyzgglM,XMTDvb">
                        <field name="OP">GTE</field>
                        <value name="A">
                          <block type="math_single" id="a0@ts-ulSz~m0[mw87ir">
                            <field name="OP">ABS</field>
                            <value name="NUM">
                              <shadow type="math_number" id="ft^DVzOH^GlSjzUC}@3c">
                                <field name="NUM">9</field>
                              </shadow>
                              <block type="read_details" id="A/Hs,Vny^(7-mM{:InU[">
                                <field name="DETAIL_INDEX">4</field>
                              </block>
                            </value>
                          </block>
                        </value>
                        <value name="B">
                          <block type="variables_get" id="HeD6}Fq/mG)kOI1]*44[">
                            <field name="VAR" id="W4$:ZQCmEz#8+=4ysv5Y" variabletype="">stop loss</field>
                          </block>
                        </value>
                      </block>
                    </value>
                    <statement name="DO0">
                      <block type="variables_set" id="u:oJzS]FEYpy9ypI3bD*">
                        <field name="VAR" id="j}8O`Vs+RJljIwPu-_:_" variabletype="">initial amount</field>
                        <value name="VALUE">
                          <block type="variables_get" id="),(#N=,PVUQl!wgt-~4i">
                            <field name="VAR" id="%L?;380E6Lr^3b.%}t5Q" variabletype="">win amount</field>
                          </block>
                        </value>
                      </block>
                    </statement>
                  </block>
                </next>
              </block>
            </next>
          </block>
        </statement>
        <next>
          <block type="notify" id="]fc2SUtM2UzE|=Tzpy}S">
            <field name="NOTIFICATION_TYPE">info</field>
            <field name="NOTIFICATION_SOUND">silent</field>
            <value name="MESSAGE">
              <block type="text_join" id="*!(=c%67H[//(y{YBgZy">
                <mutation items="2"></mutation>
                <value name="ADD0">
                  <block type="text" id="[69Ue}W}MaCF*BU#294_">
                    <field name="TEXT">Total Lucro: </field>
                  </block>
                </value>
                <value name="ADD1">
                  <block type="total_profit" id="}*H,Z~xMxuNBTwVTv4*{"></block>
                </value>
              </block>
            </value>
            <next>
              <block type="controls_if" id="Su2G{`dLNbP}g7q=]!p)">
                <mutation else="1"></mutation>
                <value name="IF0">
                  <block type="logic_compare" id="N^U?{:24gAXhqr=~#}={">
                    <field name="OP">LT</field>
                    <value name="A">
                      <block type="total_profit" id="%wR%e|eExAHt5W:,kAsm"></block>
                    </value>
                    <value name="B">
                      <block type="variables_get" id=",F_S*,CaK.}p}MS{#)eG">
                        <field name="VAR" id="mXtFswo{p,|%W1:V-$+r" variabletype="">profit</field>
                      </block>
                    </value>
                  </block>
                </value>
                <statement name="DO0">
                  <block type="trade_again" id="WlL(Yr4%r-~ea4QwP#Nm"></block>
                </statement>
                <statement name="ELSE">
                  <block type="text_print" id="Flww-KT}T1+c~bF:^cMb">
                    <value name="TEXT">
                      <shadow type="text" id="kqlrIk.GO.^}hI,PoUV)">
                        <field name="TEXT">abc</field>
                      </shadow>
                      <block type="text_join" id="_3~!q2F=HY|q(Kdb^m9l">
                        <mutation items="2"></mutation>
                        <value name="ADD0">
                          <block type="text" id="Gg@4VoMw!c3UbQ[:@PB.">
                            <field name="TEXT">Concluido! Lucro Total : </field>
                          </block>
                        </value>
                        <value name="ADD1">
                          <block type="total_profit" id="O:MYUukPm?_m(w65eRd?"></block>
                        </value>
                      </block>
                    </value>
                  </block>
                </statement>
              </block>
            </next>
          </block>
        </next>
      </block>
    </statement>
  </block>
  <block type="before_purchase" id="strategy" collapsed="true" x="0" y="701">
    <statement name="BEFOREPURCHASE_STACK">
      <block type="purchase" id="ZVP}e)NE+mzs2cOebw5Y">
        <field name="PURCHASE_LIST">DIGITDIFF</field>
      </block>
    </statement>
  </block>
</xml>
<!---
Alaudeen12/Alaudeen12 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
