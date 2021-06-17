# Nxvem
Discord Avatar background cheat for android
#1 download : https://play.google.com/store/apps/details?id=com.prodevutils.inspecto
#2 login to discord with your username and password
#3 open the inspect element and head to the console area
#4 paste : const DI = window.DiscordInternals;
const hasLib = !!(DI && DI.versionCompare && DI.versionCompare(DI.version || "", "1.9") >= 0);
    const WebpackModules = hasLib && DI.WebpackModules || (() => {

        const req = typeof(webpackJsonp) == "function" ? webpackJsonp([], {
                '__extra_id__': (module, exports, req) => exports.default = req
        }, ['__extra_id__']).default : webpackJsonp.push([[], {
                '__extra_id__': (module, exports, req) => module.exports = req
        }, [['__extra_id__']]]);
        delete req.m['__extra_id__'];
        delete req.c['__extra_id__'];
        const find = (filter, options = {}) => {
            const {cacheOnly = false} = options;
            for (let i in req.c) {
                if (req.c.hasOwnProperty(i)) {
                    let m = req.c[i].exports;
                    if (m && m.__esModule && m.default && filter(m.default))
                        return m.default;
                    if (m && filter(m))
                        return m;
                }
            }
            if (cacheOnly) {
                console.warn('Cannot find loaded module in cache');
                return null;
            }
            console.warn('Cannot find loaded module in cache. Loading all modules may have unexpected side effects');
            for (let i = 0; i < req.m.length; ++i) {
                let m = req(i);
                if (m && m.__esModule && m.default && filter(m.default))
                    return m.default;
                if (m && filter(m))
                    return m;
            }
            console.warn('Cannot find module');
            return null;
        };
        const findByUniqueProperties = (propNames, options) => find(module => propNames.every(prop => module[prop] !== undefined), options);
        const findByDisplayName = (displayName, options) => find(module => module.displayName === displayName, options);
        return {find, findByUniqueProperties, findByDisplayName};
    })();
t = WebpackModules.findByUniqueProperties(["isDeveloper"]);
Object.defineProperty(t,"isDeveloper",{get:_=>1,set:_=>_,configurable:true});
#5 let the page refresh by itself
#6 head to settings and tap on the experiment option
#7 tap on custom profile premium and select on the treatment 1 option let the page reaload
#8 head to settings/my profile and u can see the Avatar background option
