<template>
    <div class="paysuccess">
        <div class="success">
            <h3>
                <img src="./images/right.png" width="48" height="48">
                恭喜您，支付成功啦！
            </h3>
            <div class="paydetail">
                <p class="button">
                    <router-link class="btn-look" to="/center">查看订单</router-link>
                    <router-link class="btn-goshop" to="/">继续购物</router-link>
                </p>
            </div>
        </div>
    </div>
</template>
    
<script>
    export default {
        name: 'PaySuccess',
        // 组件内路由守卫
        beforeRouteEnter(to, from, next) {
            // 在渲染该组件的对应路由被验证前调用
            // 不能获取组件实例 `this` ！
            // 因为当守卫执行时，组件实例还没被创建！
            if(from.path == '/pay' || from.path == '/') {
                next()
            }else {
                next(false)
            }
        },
        /* beforeRouteUpdate(to, from) {
            // 在当前路由改变，但是该组件被复用时调用
            // 举例来说，对于一个带有动态参数的路径 `/users/:id`，在 `/users/1` 和 `/users/2` 之间跳转的时候，
            // 由于会渲染同样的 `UserDetails` 组件，因此组件实例会被复用。而这个钩子就会在这个情况下被调用。
            // 因为在这种情况发生的时候，组件已经挂载好了，导航守卫可以访问组件实例 `this`
        },
        beforeRouteLeave(to, from) {
            // 在导航离开渲染该组件的对应路由时调用
            // 与 `beforeRouteUpdate` 一样，它可以访问组件实例 `this`
        }, */
    }
</script>

<style lang="less" scoped>
    .paysuccess {
        margin: 20px auto;
        padding: 25px;
        border: 1px solid rgb(211, 211, 211);
        width: 1200px;
        width: 1148px;

        .success {
            width: 500px;
            margin: 0 auto;

            h3 {
                margin: 20px 0;
                font-weight: 700;
                font-size: 20px;
                line-height: 30px;

                img {
                    max-width: 100%;
                    vertical-align: middle;
                    border: 0;
                    margin-right: 14px;
                }
            }

            .paydetail {
                margin-left: 66px;
                font-size: 15px;

                .button {
                    margin: 30px 0;
                    line-height: 26px;

                    a {
                        display: inline-block;
                        box-sizing: border-box;
                        text-align: center;
                        vertical-align: middle;
                        cursor: pointer;
                        border-radius: 2px;
                        user-select: none;
                        font-size: 18px;
                        padding: 4px 20px;
                        line-height: 22px;
                        text-decoration: none;

                        &.btn-look {
                            margin-right: 13px;
                            color: #fff;
                            background-color: #e1251b;
                            border: 1px solid #e1251b;
                        }

                        &.btn-goshop {
                            color: #666;
                            background-color: #eee;
                            border: 1px solid #e1e1e1;
                        }
                    }
                }
            }
        }
    }
</style>