# zadaniya-2
// 1 задание — проверка уникальности массива
function uniqueArray(arr) {
    return [...new Set(arr)];
}
console.log(uniqueArray([1, 2, 2, 3, 1]));

// 2 задание — фильтр положительных чисел
function positiveNumbers(arr) {
    return arr.filter(number => number > 0);
}
console.log(positiveNumbers([-3, 5, 0, 8, -1]));

// 3 задание — сумма и среднее значение массива
function sumAndAverage(arr) {
    let sum = arr.reduce((total, number) => total + number, 0);
    let average = arr.length > 0 ? sum / arr.length : 0;
    return {
        sum: sum,
        average: average
    };
}
console.log(sumAndAverage([2, 4, 6, 8]));

// 4 задание — максимум из трёх значений
function maxOfThree(a, b, c) {
    return Math.max(a, b, c);
}
console.log(maxOfThree(7, 12, 4));

// 5 задание — проверка чётности
function isEven(number) {
    return number % 2 === 0;
}
console.log(isEven(6));
console.log(isEven(7));

// 6 задание — подсчёт слов в строке
function countWords(str) {
    let words = str.toLowerCase().match(/[а-яёa-z0-9]+/gi) || [];
    let result = {};
    for (let word of words) {
        if (result[word]) {
            result[word]++;
        } else {
            result[word] = 1;
        }
    }
    return result;
}
console.log(countWords("Привет мир, привет JavaScript"));

// 7 задание — второе по величине уникальное число
function secondLargest(arr) {
    let numbers = [...new Set(arr)].sort((a, b) => b - a);
    if (numbers.length < 2) {
        return null;
    }
    return numbers[1];
}
console.log(secondLargest([5, 8, 3, 8, 5, 2]));

// 8 задание — подсчёт среднего балла
function averageGrade(grades) {
    if (grades.length === 0) {
        return 0;
    }
    let sum = grades.reduce((total, grade) => total + grade, 0);
    return sum / grades.length;
}
console.log(averageGrade([4, 5, 3, 5]));

// 9 задание — транслитерация русского текста в английский
function transliterate(str) {
    let letters = {
        а: "a", б: "b", в: "v", г: "g", д: "d",
        е: "e", ё: "yo", ж: "zh", з: "z", и: "i",
        й: "y", к: "k", л: "l", м: "m", н: "n",
        о: "o", п: "p", р: "r", с: "s", т: "t",
        у: "u", ф: "f", х: "kh", ц: "ts", ч: "ch",
        ш: "sh", щ: "shch", ъ: "", ы: "y", ь: "",
        э: "e", ю: "yu", я: "ya"
    };
    return str.toLowerCase().split("").map(letter => {
        return letters[letter] !== undefined ? letters[letter] : letter;
    }).join("");
}
console.log(transliterate("Привет, мир"));

// 10 задание — сокращение ФИО
function shortName(fullName) {
    let parts = fullName.trim().split(/\s+/);
    if (parts.length < 2) {
        return fullName;
    }
    let result = parts[0] + " " + parts[1][0] + ".";
    if (parts[2]) {
        result += parts[2][0] + ".";
    }
    return result;
}
console.log(shortName("Иванов Иван Иванович"));
